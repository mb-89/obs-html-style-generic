# obs-html-style-generic

The generic style of [obs-html](https://github.com/mb-89/obs-html), obs's HTML adapter: a plain,
content-first look with system serif body text, laid over obs-html's structural stylesheet. It is
an ordinary obs style component, a release whose tree holds `style.css` at its root, and nothing
about it is built into obs-html.

## Install and select

```sh
obs-components install obs-html-style-generic
```

A Document's manifest selects it like any other style component:

```yaml
obs:
  style: obs-html-style-generic
```

obs-html requires this component (its `se.toml`, `[components.obs-html-style-generic]`) and
applies it as its default: a build with neither `obs-html --style FOLDER` nor `obs.style` uses the
installed `obs-html-style-generic`, and fails naming `obs-components install
obs-html-style-generic` where it is not installed.

## A new style

This repository is the example to copy for a new style: a repository named after the style, with
the topic `component`, holding `style.css` (and optionally `assets.json` and `cover.html`, see
obs-html's `spec/artifact-ui.md`, Styling) and a `component.toml` whose `name` is the repository's
name, released as tags `v<major>.<minor>.<patch>`. A style must not declare page geometry
(`@page`, `size`, `--paper-*`): a Document's profile owns it.

## License

[MIT](LICENSE).