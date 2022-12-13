# Installation

You can set up all components of Open Podcast on your own infrastructure!  
The following sections describe how to do that.

## Stack

The easiest way to set up Open Podcast is to use our [stack] repository.
It contains a Docker Compose file that sets up all components of Open Podcast
and a script that runs the connectors as cron jobs.

The following services are included in this repository:

- [API]: The API that is used to store the data in the database
- [Forwarder]: A proxy in front of your podcast host which forwards realtime RSS request data to the API
- [Spotify-Connector]: The connector to fetch data from Spotify
- [Apple-Connector]: The connector to fetch data from Apple
- [Apple-Automation]: The automation to fetch a session cookie from Apple
- [Metabase]: The analytics tool that is used to visualize the data
- [MySQL]: The database

## Individual Components

Alternatively, you can set up each component individually.
Find the instructions for each component below.

### Forwarder

The forwarder runs as a Cloudflare worker.
See the [instructions][forwarder] in the forwarder repository.

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
[forwarder]: https://github.com/openpodcast/forwarder
[spotify-connector]: https://github.com/openpodcast/spotify-connector
[apple-connector]: https://github.com/openpodcast/apple-connector
[metabase]: https://github.com/metabase/metabase
[mysql]: https://hub.docker.com/_/mysql
[apple-automation]: https://github.com/openpodcast/apple-automation
[stack]: https://github.com/openpodcast/stack
