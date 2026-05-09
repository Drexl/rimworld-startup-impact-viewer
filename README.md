# Loading Progress Startup Impact XML Viewer

A standalone desktop app for viewing `StartupImpactData.xml` produced by the
[Loading Progress](https://github.com/ilyvion/loading-progress) RimWorld mod.

The app auto-loads the XML from RimWorld's default location, auto-detects Steam and GOG installs to map mods to their Workshop pages, and lets you drill into per-category timing for each mod the same way Loading Progress does.
You will of course need to run Rimworld at least once to save the StartupImpactData.xml.
I made this for myself. I'm unlikely to make many changes to it unless there is a problem. I'm happy with how it is.
Linux users can build from source and it'll probably work for the basics (not auto path detection).

## Features

- **Auto-loads** `StartupImpactData.xml` from `%AppData%\..\LocalLow\Ludeon Studios\RimWorld by Ludeon Studios\` on launch.
- **Auto-detects** RimWorld Mods folders via the Windows registry (Steam library VDF + GOG game registry) and merges multiple installs.
- **Custom Mods folders** can be added manually for non-standard installs.
- **Mod names link to the Steam Workshop** page when the Workshop ID is known, name search otherwise.
- **Sortable, filterable table** with per-category breakdown, log-scale option, and tooltips.

## Building from source

Requires the [Neutralino CLI](https://neutralino.js.org/docs/getting-started/installation):

```sh
npm install -g @neutralinojs/neu
```

Then, from the repo root:

```sh
neu update     # downloads the platform binaries into /bin
neu build      # produces /dist/StartupImpactViewer/
```

The Windows distributable is `dist/StartupImpactViewer/StartupImpactViewer-win_x64.exe`
plus `resources.neu`. Both must ship together.
