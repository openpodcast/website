# How It Works

## High-Level Overview

Open Podcast consists of three main components:

- [forwarder]: A proxy for podcast RSS feeds and audio files to collect
  additional data for analytics.
- [importer](https://github.com/openpodcast/spotify-importer): Fetches and
  imports metrics from platforms like Spotify and Apple Music to provide a
  consolidated data lake for analytical data.
- gateway: A reference implementation of a server which collects fine-grained
  data from podfetchers that implement the Open Podcast API.

The implementation has three parts and consists of:

- a proof of concept or prototype which is developed as fast as possible to get
  feedback from potential users
- an MVP which can be tested on first users and podcasts
- a final version which can be used in production

The following sections describe the techncal implementation of the proof of
concept of the respective component.

## Forwarder

The prototype of the forwarder will be written in Rust. The reason is
that the forwarder can be deployed as an edge worker on platforms like
Cloudflare or Fastly, which allows us to be very close to the Podcast platforms
(Spotify, Apple,...) and at the same time not have to deal with deployments or
load-balancing. Rust helps us prevent common security issues when receiving and
parsing client data. The language is also fast and memory-efficient, which is a
great bonus.

In order to run the forwarder on other hosters (like DigitalOcean, AWS, or
Hetzner) in the future, we might pivot to Golang for the final implementation.
Go runs on any ordinary webserver and is written by a broad range of developers.
With that we hope to receive more contributions by external developers in the
future. Go is also great for network services. The downside is that it doesn't
run on edge computing networks that easily, so we might face higher latency.

## Importer

The forwarder has to fetch data from Spotify, Apple et. al. As such it needs to
either run as a browser extension or a standalone application. When running the
importer as a browser extension, we are limited by the languages supported by
all browsers, which leaves us with JavaScript (and TypeScript). Since we could
re-use the same parsing code inside a standalone application with
JavaScript/TypeScript in the future, we are inclined to write the importers in
TypeScript. It is compatible with all major browser and provides a solid level
of type safety.

## Gateway

The gateway is a plain metric collector.
It just receives `POST` requests with metrics and forwards them to a
database.
We have not decided on a technology stack for it yet, but it should be
straightforward to implement in any language. We will provide a reference
implementation for testing purposes but the specification for accepted events
will be more important than the actual language used for implementation.
For the first proof of concept we might use an all in one solution like Posthog or Matomo.

[forwarder]: https://github.com/openpodcast/forwarder
