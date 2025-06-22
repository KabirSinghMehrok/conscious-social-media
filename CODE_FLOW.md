This is a browser extension that shows a popup when you click on its icon in the browser toolbar.

The main logic is in `src/popup/Popup.jsx`, which is a React component.

The project is set up to be built with webpack.

When you run `npm run build`:

1.  webpack takes `src/popup/Popup.jsx` as the entry point.
2.  It bundles all the necessary JavaScript (React and the app's code) into a single file: `dist/popup.bundle.js`.
3.  It uses `src/popup/popup.html` as a template and injects the bundled JavaScript into it, creating `dist/popup.html`.
4.  It copies `public/manifest.json` to `dist/manifest.json`.

The final extension is in the `dist` folder.

When you load the extension in your browser:

1.  The browser reads `dist/manifest.json`.
2.  This file tells the browser to show `dist/popup.html` when the extension icon is clicked.
3.  When you click the icon, `popup.html` is loaded.
4.  The JavaScript in `popup.bundle.js` runs, which renders the React `Popup` component into the `<div id=oot\></div>` of the HTML.
