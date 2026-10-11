# Trace apps for Unraid

Unraid Community Applications templates for the four Trace apps. Each app is a self-hosted web app in a single Docker container, open source under AGPL-3.0.

| App | What it is | Default port |
| --- | --- | --- |
| [NutriTrace](https://github.com/TraceApps/nutritrace) | Personal nutrition tracker | 3001 |
| [LiftTrace](https://github.com/TraceApps/lifttrace) | Weightlifting tracker | 3002 |
| [CookTrace](https://github.com/TraceApps/cooktrace) | Recipes, pantry and cooking | 3003 |
| [NoteTrace](https://github.com/TraceApps/notetrace) | Notes, checklists and reminders | 3004 |

## Install

1. In Unraid, open the **Apps** tab and search for the app by name.
2. Click **Install**.
3. Fill in **JWT Secret** with a long random string, for example the output of `openssl rand -base64 48`. Keep it the same from then on: changing it signs everyone out.
4. Click **Apply**, then open the app from its **WebUI** link and create your account.

Data lives in `/mnt/user/appdata/<app>/db` (the SQLite database) and `/mnt/user/appdata/<app>/uploads` (photos and files). Back up both.

**Insecure Cookies** starts at `1`, so signing in works over plain `http://` on your LAN, which is how the WebUI link opens the app. Session cookies then travel unencrypted, so keep the app on a network you trust. Once the app sits behind an HTTPS reverse proxy, set it to `0`. More: [Plain-HTTP LAN](https://traceapps.github.io/docs/getting-started/lan-http/).

Every other setting the apps support (email, single sign-on, backups) is in each app's Settings or in the [documentation](https://traceapps.github.io/docs/). Any of their environment variables can be added to the container with **Add another Path, Port, Variable, Label or Device**.

## Support

- Questions and help with an app: the Discussions on its GitHub repository ([NutriTrace](https://github.com/TraceApps/nutritrace/discussions), [LiftTrace](https://github.com/TraceApps/lifttrace/discussions), [CookTrace](https://github.com/TraceApps/cooktrace/discussions), [NoteTrace](https://github.com/TraceApps/notetrace/discussions)).
- A problem with a template itself: [open an issue here](https://github.com/TraceApps/unraid-templates/issues).

## License

[AGPL-3.0](LICENSE), the same license as the apps.
