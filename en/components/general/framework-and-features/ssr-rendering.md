---
title: Server-side rendering with Angular Universal.
_description: How to use Angular Universal rendering with Ignite UI for Angular.
_keywords: Ignite UI for Angular, Universal, Server-side rendering
---

## Server-side Rendering with Angular Universal

This topic aims to describe what server-side rendering is and how to configure it within Ignite UI for Angular application. 

### Angular Universal

Most of the Angular applications run in a client's browser, but if you want to generate the full HTML for a page on the server, and avoid additional round-trips for data fetching - [Angular Universal](https://angular.io/guide/universal) come in handy. It renders a client-side page to HTML on the server that is later bootstrapped on the client. Okay, but how it works?

### How it works?

With Angular Universal, you will serve a static version of your apps' landing page, while at the same time the full Angular application loads in the background. The landing pages will be pure HTML and will be displayed even if the JavaScript is disabled, keep in mind that [handling browser events](ssr-rendering.md#things-to-note) won't be possible. More about Server Rendering you can find [here](https://developers.google.com/web/updates/2019/02/rendering-on-the-web).

### Usage

Server-side rendering is one of the many techniques part of [Rendering on Web](https://developers.google.com/web/updates/2019/02/rendering-on-the-web) guidelines, that can:
- Increase the chance of search engines to access your website - by easing web crawlers through Search Engine Optimization (SEO). 
- Show the first page quickly - slow initial page load is disengaging for the users (if it takes more than 3 seconds to load).
- Improve your app performance - which has a positive impact on the initial user experience.

### Add SSR to existing Ignite UI application

#### Step 1 - Add @nguniversal 
By using Angular CLI schematic we can run the following command:

```
ng add @nguniversal/express-engine --clientProject ssr-example
```

This schematic will perform several changes to your app client and server configurations, as well as npm commands and app.module updates.

#### Step 2 - Define all browser-specific objects that are missing
Since Universal apps run on the server and not in the browser, there are a few things you need to watch out for in your code. Browser-specific objects, such as `window`, `document`, or `location` are missing, so we can use [domino](https://github.com/fgnass/domino#server-side-dom-implementation-based-on-mozillas-domjs) for server-side dom abstraction. Domino is a Server-side DOM implementation based on Mozilla's dom.js.

```typescript
const domino = require('domino');
const fs = require('fs');
const path = require('path');
const template = fs
  .readFileSync(path.join('dist/browser', 'index.html'))
  .toString();
const window = domino.createWindow(template);
window.Object = Object;
window.Math = Math;

// Ignite UI browser objects abstractions
(global as any).window = window;
(global as any).document = window.document;
(global as any).HTMLElement = window.HTMLElement;
(global as any).HTMLElement.prototype.getBoundingClientRect = () => {
    return {
      left: '',
      right: '',
      top: '',
      bottom: ''
  };
};

// If using IgxIconService to register icons
(global as any).XMLHttpRequest = require('xmlhttprequest').XMLHttpRequest;

// Other optional depending on your application configuration
(global as any).object = window.object;
(global as any).navigator = window.navigator;
(global as any).localStorage = window.localStorage;
(global as any).DOMTokenList = window.DOMTokenList;
```

#### Step 3 - Start your universal app
Run the following command:

```
npm run build:ssr && npm run serve:ssr
```

### Build a new application from scratch 

1. Use `ng new` or the [Ignite UI CLI](../cli-overview.md) `ig new` command.
2. Execute `ng add igniteui-angular` which installs the library's npm packages to your workspace and configures the project in the current working directory to use that library.
4. Add Angular Universal with `ng add @nguniversal/express-engine --clientProject ig-ssr-example`. `ig-ssr-example` is your project name.
3. Add Ignite UI for Angular components - e.g. Grid, Calendar et
4. Configure the `server.ts` file to define all needed browser-specific objects, such as `window`, `document`, or `location`.
	- install domino `npm install domino` - for server-side dom abstraction
	- install xmlhttprequest `npm i xmlhttprequest` - If using IgxIconService to register icons

### Use starter project

Use the starter project that includes Ignite UI for Angular components. The project uses Angular CLI to quickly build a simple application with Angular Universal.

#### Step 1 - Clone the starter repository

```
git clone https://github.com/zdrawku/ng-universal-example.git
```

#### Step 2 - Use NPM to install the needed dependencies 

```
npm install
```

#### Step 3 - Build and start the application by using:

```
npm run build:ssr && npm run serve:ssr
```


### Things to note 

- If your application is using other browser-specific objects, wrap their usage in a conditional statement, so that they’ll only be used by Angular on the browser. You can do this by importing the functions `isPlatformBrowser` and `isPlatformServer` from `@angular/common`, injecting the `PLATFORM_ID` token into your component, and running the imported functions to see whether you’re on the server or the browser.
- If using ElementRef for HTML element handling, don’t use the nativeElement to manipulate attributes on the element. Instead, inject and use the [Renderer2 methods](https://alligator.io/angular/using-renderer2).
- All URLs for server requests should be absolute, keep in mind that data requests from relative URLs will fail when running from the server.
- For handling browser events the Angular team provides the [preboot](https://github.com/angular/preboot) library. This library buffers the events and replay them once the client-side script is loaded.
- When using Angular Universal, the server will pre-render pages that will be visible to the users, however, interactions will be limited. Once the client-side app is loaded in the background, it will seamlessly switch from showing the server-rendered pages to the client-side app.

### Useful resources

<div class="divider--half"></div>

* [Angular Universal guide](https://angular.io/guide/universal)
* [Ignite UI Starter Kit](https://github.com/zdrawku/ng-universal-example)
* [Server-side rendering terminology](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)
* [Getting started with Ignite UI for Angular](getting_started.md)
* [Ignite UI CLI Guide](step-by-step-guide.md)