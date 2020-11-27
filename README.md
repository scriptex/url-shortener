# Personal URL shortener

## Manage Links

Links are managed through [`src/links.json`](src/links.json), which is seeded
with a few examples to start:

```json
{
  "/": "https://atanas.info",
  "in": "https://linkedin.com/in/scriptex",
  "tw": "https://twitter.com/scriptexbg"
}
```

It couldn't be simpler: the key is the "shortlink" path that gets redirected,
and the value is the target URL. Keys can be as short or as long as you want,
using whatever mixture of characters you want. `/` is a special entry for
redirecting the root path.

Go ahead and make an edit, then commit and push to your repository. The hosting
provider you chose above should automatically build and deploy your change.
That's it!

### Config

Environment variables are used to set config options. There is only one at this
point:

| Variable | Description                                                        | Values   | Default |
| -------- | ------------------------------------------------------------------ | -------- | ------- |
| `USE_JS` | Whether to redirect with JavaScript instead of a `<meta>` refresh. | `1`, `0` | `0`     |

### Install Manually

To install somewhere else, or just on your own machine:

1. Fork this repository to create your own copy and clone to your machine.

2. Make sure you have a compatible version of [Node.js](https://nodejs.org/)
   (see `engines.node` in [`package.json`](package.json)).
   [nvm](https://github.com/nvm-sh/nvm) is the recommended installation method
   on your own machine:

   ```bash
   $ nvm install
   ```

3. Install dependencies with npm:

   ```bash
   $ npm install
   ```

4. Build the static site:

   ```bash
   $ npm run build
   ```

5. Deploy the generated `_site` directory to its final destination.

## Development

The following includes a few instructions for developing. For 11ty-specific
details – the static site generator that powers the url shortener – see their
[docs](https://www.11ty.dev/docs/).

### Install

Follow the "Install Manually" section above to setup on your own machine.

### Start

Start the development server:

```bash
$ npm run dev
```

### Code Style

[Prettier](https://prettier.com/) is setup to enforce a consistent code style.
It's highly recommended to
[add an integration to your editor](https://prettier.io/docs/en/editors.html)
that automatically formats on save.

To run via the command line:

```bash
$ npm run lint
```

## Releasing

After development is done in the `development` branch and is ready for release,
it should be merged into the `master` branch, where the latest release code
lives. [Release It!](https://github.com/release-it/release-it) is then used to
interactively orchestrate the release process:

```bash
$ npm run release
```
