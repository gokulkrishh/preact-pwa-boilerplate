# Preact PWA Boilerplate / Starter Kit

[![Build Status](https://travis-ci.org/gokulkrishh/preact-pwa-boilerplate.svg?branch=master)](https://travis-ci.org/gokulkrishh/preact-pwa-boilerplate)
[![gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/developit/preact)

> :guitar: Ready-to-rock [Preact] starter project, powered by [webpack].
>
> :rocket: If you're starting a new project using [Preact], you've come to the right place.
Below is a step-by-step guide that takes you straight from downloading this boilerplate to production.
>
> **[:boom: View Demo :boom:](https://preact-pwa.surge.sh)**


---

## What changes are done?

Added ```serviceWorker``` for offline support, ```manifest.json``` file for add to homescreen support, cool icons from preact site and updated preact to latest version(7.1.0) + yarn ;). Rest all the same!!

Thanks to [Jason Miller](https://github.com/developit) for writing a simple and awesome boilerplate.

## What else do you want?

- [ ] - Travis with lighthouse support
- [ ] - Feel free to create issue and make this repo awesome ;)

# Quick-Start Guide

- [Installation](#installation)
- [Development Workflow](#development-workflow)
- [Structure](#structure)
- [CSS Modules](#css-modules)
- [Handling URLS](#handling-urls)


## Installation

**1. Clone this repo:**

```sh
git clone --depth 1 https://github.com/developit/preact-boilerplate.git my-app
cd my-app
```


**2. Make it your own:**

```sh
rm -rf .git && git init && npm init
```

> :information_source: This re-initializes the repo and sets up your NPM project.


**3. Install the dependencies:**

```sh
npm install
```

> You're done installing! Now let's get started developing.



## Development Workflow


**4. Start a live-reload development server:**

```sh
npm run dev
```

> This is a full web server nicely suited to your project. Any time you make changes within the `src` directory, it will rebuild and even refresh your browser.

**5. Testing with `mocha`, `karma`, `chai`, `sinon` via `phantomjs`:**

```sh
npm test
```

**6. Generate a production build in `./build`:**

```sh
npm run build
```

> You can now deploy the contents of the `build` directory to production!
>
> **[Surge.sh](https://surge.sh) Example:** `surge ./build -d my-app.surge.sh`


**5. Start local production server with `superstatic`:**

```sh
npm start
```

> This is to simulate a production (CDN) server with gzip. It just serves up the contents of `./build`.



---


## Structure

Apps are built up from simple units of functionality called Components. A Component is responsible for rendering a small part of an application, given some input data called `props`, generally passed in as attributes in JSX. A component can be as simple as:

```js
class Link extends Component {
  render({ to, children }) {
    return <a href={ to }>{ children }</a>;
  }
}
// usage:
<Link to="/">Home</Link>
```


---


## CSS Modules

This project is set up to support [CSS Modules](https://github.com/css-modules/css-modules).  By default, styles in `src/style` are **global** (not using CSS Modules) to make global declarations, imports and helpers easy to declare.  Styles in `src/components` are loaded as CSS Modules via [Webpack's css-loader](https://github.com/webpack/css-loader#css-modules).  Modular CSS namespaces class names, and when imported into JavaScript returns a mapping of canonical (unmodified) CSS classes to their local (namespaced/suffixed) counterparts.

When imported, this LESS/CSS:

```css
.redText { color:red; }
.blueText { color:blue; }
```

... returns the following map:

```js
import styles from './style.css';
console.log(styles);
// {
//   redText: 'redText_local_9gt72',
//   blueText: 'blueText_local_9gt72'
// }
```

Note that the suffix for local classNames is generated based on an md5 hash of the file. Changing the file changes the hash.


---


## Handling URLS

:information_desk_person: This project contains a basic two-page app with [URL routing](http://git.io/preact-router).

Pages are just regular components that get mounted when you navigate to a certain URL. Any URL parameters get passed to the component as `props`.

Defining what component(s) to load for a given URL is easy and declarative. You can even mix-and-match URL parameters and normal props.

```js
<Router>
  <A path="/" />
  <B path="/b" id="42" />
  <C path="/c/:id" />
</Router>
```


---


## License

MIT


[Preact]: https://developit.github.io/preact
[webpack]: https://webpack.github.io
