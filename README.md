# next-ga

> The Next.js team has an official plugin being developed, while plugin supports it's still in canary only, the way the plugin works it's simpler than next-ga and I recommend you to check it and do it manually in your project until it's stable.

> Plugin link: https://github.com/zeit/next.js/tree/canary/packages/next-plugin-google-analytics

Next.js High Order Component to integrate Google Analytics on every page change.

<a href="https://www.patreon.com/sergiodxa">
	<img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="160">
</a>

## Usage

Install it

```bash
yarn add next-ga
```

Import it inside your `pages/_app.js`;

```js
import Router from "next/router";
import withGA from "next-ga";
```

Wrap your [custom App container](https://nextjs.org/docs#custom-%3Capp%3E) with it

```js
// pass your GA code as first argument
export default withGA("UA-xxxxxxxxx-1", Router)(MyApp);
```

That's it, now when the user access a page it will log a pageview to Google Analytics, each page change after that will also trigger a pageview on Google Analytics.

> **Note**: This module detects if it's running in localhost and do nothing there to avoid polluting your analytics with local data.
