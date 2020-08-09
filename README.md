# denismorozov/routify-starter

This template forks the official Routify rollup starter and extends it with the following:
- TypeScript
- SCSS w/ PostCSS autoprefixing, and opinionated style project structure

## Get started

1. Clone, fork, or npx degit this repository: `git clone git@github.com:denismorozov/routify-starter.git`
2. Go through the items in [docs/new-project-todo.md](docs/new-project-todo.md).

## TODO eventually
- Testing, maybe cypress
- Linting, both eslint and prettier seem to not work with svelte-preprocess yet
- Document pulling in upstream updates (from official routify starter)


# routify-starter

Starter template for [Routify](https://github.com/sveltech/routify)

### Get started

#### Starter templates
| Template                                  | Description                                                 |
|-------------------------------------------|-------------------------------------------------------------|
| [master](https://example.routify.dev/)    | Default template, includes examples folder                  |
| [blog](https://blog-example.routify.dev/) | Generates a blog from local markdown posts. Includes mdsvex |
| [auth](https://auth-example.routify.dev/) | Embedded login on protected pages. Includes Auth0           |

To use a template, run

`npx @sveltech/routify init`

or

`npx @sveltech/routify init --branch <branch-name>`.

### npm scripts

| Syntax           | Description                                                                       |
|------------------|-----------------------------------------------------------------------------------|
| `dev`            | Development (port 5000)                                                           |
| `dev:nollup`     | Development with crazy fast rebuilds (port 5000)                                  |
| `dev-dynamic`    | Development with dynamic imports                                                  |
| `build`          | Build a bundled app with SSR + prerendering and dynamic imports                   |
| `serve`          | Run after a build to preview. Serves SPA on 5000 and SSR on 5005                  |
| `deploy:*`       | Deploy to netlify or now                                                          |
| `export`         | Create static pages from content in dist folder (used by `npm run build`)         |

### SSR and pre-rendering

SSR and pre-rendering are included in the default build process.

`npm run deploy:(now|netlify)` will deploy the app with SSR and prerendering included.

To render async data, call the `$ready()` helper whenever your data is ready.

If $ready() is present, rendering will be delayed till the function has been called.

Otherwise it will be rendered instantly.

See [src/pages/example/api/[showId].svelte](https://github.com/sveltech/routify-starter/blob/master/src/pages/example/api/%5BshowId%5D.svelte) for an example.

### Production

* For SPA or SSR apps please make sure that url rewrite is enabled on the server.
* For SPA redirect to `__dynamic.html`.
* For SSR redirect to the lambda function or express server.

### Issues?

File on Github! See https://github.com/sveltech/routify/issues .
