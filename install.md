## Installation

You can set up all components of Open Podcast on your own infrastructure. The
following sections describe how to do that.

### Forwarder

The forwarder runs as a Cloudflare worker.
See the [instructions][forwarder-instructions] in the forwarder repository.

### Connectors

So far we offer the following connectors:

- [Spotify Connector][spotify-connector]: Fetches and imports metrics from
  Spotify (https://podcasters.spotify.com)
- [Apple Connector][apple-connector]:
  Fetches and imports metrics from Apple Music
  (https://podcastsconnect.apple.com/)

You can run these connectors as a standalone application or as a cron job. If
you want to run them as a cron job, you can fork our own [cron job
repository](https://github.com/openpodcast/open) or create an issue to get
hooked up with our cron job for your podcast.

### API

The API is a plain metric collector written in TypeScript. It just receives
`POST` requests with metrics and forwards them to a database. We provide a
reference implementation for testing purposes but the specification for accepted
events allows for alternative implementations.

The API requires a database to store the metrics.
See the instructions in the [api] repository for details.

[api]: https://github.com/openpodcast/api
[forwarder-instructions]: https://github.com/openpodcast/forwarder
[spotify-connector]: https://github.com/openpodcast/spotify-connector
[apple-connector]: https://github.com/openpodcast/apple-connector
