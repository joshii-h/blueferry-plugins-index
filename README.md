# blueferry-plugins-index

The curated plugin list that [BlueFerry](https://github.com/joshii-h/blueferry)
shows in its plugin store (Settings > Plugins, the terminal client and
`blueferry plugins available`). BlueFerry reads `plugins-index.json` from

    https://raw.githubusercontent.com/joshii-h/blueferry-plugins-index/main/plugins-index.json

Other indexes can be added with `blueferry plugins index add URL`.

## Format

```json
{"version": 1, "plugins": [
  {"id": "io.example.plugin", "name": "Name", "description": "One sentence.",
   "repo": "https://github.com/me/blueferry-plugin-x", "ref": "v1.0.0",
   "capabilities": ["photos"], "icon": "folder-pictures", "emoji": "",
   "screenshot": "", "min_blueferry": "0.8", "api_version": 1}
]}
```

- `repo` must be an https Git URL; `ref` a release tag. An entry with
  `"ref": null` is listed as "coming soon" and cannot be installed.
- `icon` is a freedesktop icon name; `emoji` an alternative.
- BlueFerry treats the index as untrusted: it validates every field, shows
  text as plain text, and installs nothing without asking. Before a plugin
  is installed BlueFerry shows its source, tag, commit, capabilities and
  the command it will run.

To list a plugin, open a pull request that adds its entry with a release tag.
