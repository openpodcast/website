# How It Works

## High-Level Overview

Open Podcast consists of a few components:

- [forwarder]: A proxy for podcast RSS feeds to collect additional analytics.
- [importer]: Fetches metrics from platforms like Spotify and Apple Music.
- [gateway]: Open metrics server that can handle POST requests based on the Open Podcast API specification.

[forwarder]: https://github.com/openpodcast/forwarder
