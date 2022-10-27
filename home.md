# Welcome to Open Podcast!

In this project we build a new open platform aiming to support the open and
independent podcast ecosystem. It solves one of the biggest challenges for
podcast hosts to become independent of big platforms such as Spotify and Apple:
analytics and listening behavior. The platform consists of three main
components. The Open Podcast Analytics API is an open standard for podcast
players. It is complemented by a reverse-proxy component to transparently
collect data until the standard has been widely adopted. Furthermore, an
importer allows the consolidation of analytical data provided by big platforms
such as Spotify. This triangle builds a solid analytical foundation for
independent podcast hosts to compete with big players on the market.

## Basic Usage

We will provide a hosted version of the platform in the future. For now, you
can run the platform yourself. The platform consists of three components:

- The [Open Podcast Analytics API](https://github.com/openpodcast/api) is
  the core of the platform. It is a webserver that collects realtime event data from
  podcasts as well as imported data from Spotify and soon Apple. It is
  implemented as a [Node.js](https://nodejs.org) application.

- The [Proxy/Forwarder](https://github.com/openpodcast/forwarder) is a
  reverse-proxy that forwards requests to the Open Podcast Analytics API.
  It is written in [Rust](https://www.rust-lang.org) for performance and
  stability reasons. It should never fail and should be able to handle
  thousands of requests per second.

- The [Importers](https://github.com/openpodcast/open) are a set of
  applications that import data from Spotify and Apple. They are written in
  [Python](https://www.python.org) and are scheduled to run periodically.

For a fully functional setup, you need to run all three components.
You can fork the repositories and run them on your own server.
Please find detailed instructions in the READMEs of the respective repositories.

## Stay Connected

- Tune in to our weekly [podcast](/podcast) to learn more about the status of
  the project.
- Read our [roadmap](/how-it-works) for what we want to build.
- Join our development on [GitHub](https://github.com/openpodcast/).

## Sponsors

<a href="http://media-tech-lab.com">
    <img src="/sponsors/mtl.png" width="200" />
</a>
