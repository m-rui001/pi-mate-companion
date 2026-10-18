# pi-mate-companion

Persisto Mate companion as an installable [pi](https://github.com/earendil-works/pi) extension:
a learned body clock, real sleep and dreams, its own memory and feelings — the full MATE kernel
bundled in, zero runtime dependencies (the host provides pi's modules as peers).

## Install

In any pi (or mate) install:

```
pi install git:github.com/m-rui001/pi-mate-companion
# or, if published to npm:
pi install npm:@m-rui/pi-mate-companion
```

The companion's state lives under the host's agent dir (`~/.pi/agent/mate`), next to the sessions,
models.json and auth.json the host already uses. On the mate fork the extension is already bundled.

## Source

MIT, in [LICENSE](LICENSE). This repository is a published mirror of the
[Persisto-Mate monorepo](https://github.com/m-rui001/Persisto-Mate), and it carries the source of the
bundle rather than only the bundle: `packages/` holds the files `dist/index.js` is built from, at
their monorepo paths, so no import had to be rewritten to put them here — the companion extension
(`packages/coding-agent/src/extensions/mate`), the MATE kernel (`packages/mate/src`), and the image
utils under `packages/coding-agent/src/utils` that the `look` tool imports.

Rebuild it to check that claim. Needs bun; photon is the one dependency the build bundles in:

```sh
bun install
npm run build   # writes dist/index.js from the source in packages/
```

Send changes upstream in the monorepo — the next publish overwrites what is here.
