*Psst — looking for a more complete solution? Check out [SvelteKit](https://kit.svelte.dev), the official framework for building web applications of all sizes, with a beautiful development experience and flexible filesystem-based routing.*

*Looking for a shareable component template instead? You can [use SvelteKit for that as well](https://kit.svelte.dev/docs#packaging) or the older [sveltejs/component-template](https://github.com/sveltejs/component-template)*

---

# Svelte Component In Detail

This is a project template for [Svelte](https://svelte.dev) apps. It lives at https://github.com/sveltejs/template.

To create a new project based on this template using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit sveltejs/template svelte-app
cd svelte-app
```

*Note that you will need to have [Node.js](https://nodejs.org) installed.*


## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:8080](http://localhost:8080). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

If you're using [Visual Studio Code](https://code.visualstudio.com/) we recommend installing the official extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). If you are using other editors you may need to install a plugin in order to get syntax highlighting and intellisense.

## If you face problem when running, Please create the app using the following command

```bash
npx degit github:actionanand/first-svelte#1-skeleton my-app
cd my-app
```

## Building and running in production mode

To create an optimised version of the app:

```bash
npm run build
```

You can run the newly built app with `npm run start`. This uses [sirv](https://github.com/lukeed/sirv), which is included in your package.json's `dependencies` so that the app will work when you deploy to platforms like [Heroku](https://heroku.com).


## Single-page app mode

By default, sirv will only respond to requests that match files in `public`. This is to maximise compatibility with static fileservers, allowing you to deploy your app anywhere.

If you're building a single-page app (SPA) with multiple routes, sirv needs to be able to respond to requests for *any* path. You can make it so by editing the `"start"` command in package.json:

```js
"start": "sirv public --single"
```

## Using TypeScript

This template comes with a script to set up a TypeScript development environment, you can run it immediately after cloning the template with:

```bash
node scripts/setupTypeScript.js
```

Or remove the script via:

```bash
rm scripts/setupTypeScript.js
```

If you want to use `baseUrl` or `path` aliases within your `tsconfig`, you need to set up `@rollup/plugin-alias` to tell Rollup to resolve the aliases. For more info, see [this StackOverflow question](https://stackoverflow.com/questions/63427935/setup-tsconfig-path-in-svelte).

## Deploying to the web

### With [Vercel](https://vercel.com)

Install `vercel` if you haven't already:

```bash
npm install -g vercel
```

Then, from within your project folder:

```bash
cd public
vercel deploy --name my-project
```

### With [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public my-project.surge.sh
```

### Other Resources

- [Replacement for git clone - degit](https://dev.to/vuelancer/replacement-for-git-clone-degit-3lf1)
- [npm-run-all NPM Package](https://www.npmjs.com/package/npm-run-all)
- [Images with Lorem.space - placeholder image generator](https://lorem.space/api)

### Useful Resources & Links

1. [Official Docs (if)](https://svelte.dev/tutorial/if-blocks)
1. [Official Docs (each)](https://svelte.dev/tutorial/each-blocks)
1. [Official Docs (keys)](https://svelte.dev/tutorial/keyed-each-blocks)
1. [Tick - official doc](https://svelte.dev/tutorial/tick)
1. [2 amazing use case of tick() in Svelte that you must know](https://dev.to/tanhauhau/2-amazing-use-case-of-tick-in-svelte-that-you-must-know-8pa)
1. [Event Modifier](https://svelte.dev/tutorial/event-modifiers)
1. [Svelte Lifecycle hooks tutorial](https://reactgo.com/svelte-lifecycle-hooks-tutorial/)
1. [The Component Lifecycle in Svelte](https://betterprogramming.pub/the-component-lifecycle-in-svelte-1784ecab5862)
1. [Svelte Component Lifecycle Hooks](https://medium.com/swlh/svelte-component-lifecycle-hooks-68cfba7f3c19)
1. [How to deploy a React, Angular and Vue project to Github pages](https://deepinder.me/how-to-deploy-a-react-angular-vue-project-to-github-pages)
1. [Deploying a Svelte Application to Github Pages](https://www.devsamples.com/javascript/svelte/deploy-svelte-app-gh-pages)
1. [Publishing on Github Pages](https://alexxnb.github.io/svelte-docs/publishing/ghpages/)
> Don't forget to prefix paths in `html` file with `.` before deployment.
