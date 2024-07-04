# Connect your podcast to Open Podcast Analytics

Follow these steps to import your podcast data into your self-hosted Open
Podcast Analytics instance.

**These instructions are for podcasters who want to connect their podcast to
their self-hosted Open Podcast Analytics instance. First, you need to set up
you instance by following the [installation instructions](install.md).**

If you prefer not to handle all of this yourself, we offer a commercial solution
at [openpodcast.app](https://openpodcast.app) (German website).

## Spotify

To connect your Spotify podcast, you'll need to provide the `sp_dc` and `sp_key` cookies from your Spotify account. Here's how:

1. Install an extension to view and copy cookies, for example [Cookie Editor](https://cookie-editor.com/).
2. Log in to https://podcasters.spotify.com/dash using an account that can access the respective podcast.
3. Use the extension to view and copy the `sp_dc` and `sp_key` cookies.
4. Provide these cookie values to the [Spotify Connector](https://github.com/openpodcast/spotify-connector)

## Apple

We need the `myacinfo` and `itctx` cookies from your browser to authenticate.

1. Install an extension to view and copy cookies, for example [Cookie Editor](https://cookie-editor.com/).
2. Log in to https://podcastsconnect.apple.com/ using an account that can access the respective podcast.
3. Use the extension to view and copy the `myacinfo` and `itctx` cookies.
4. Provide these cookie values to the [Apple Connector](https://github.com/openpodcast/apple-connector)

<img src="_media/apple1.png"
     alt="Apple form to grant access to user"
     style="padding: 5px; border: 1px solid;"
/>

