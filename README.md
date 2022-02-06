# web-translate-demo

This demonstrates using the npm package web-translate
in a SvelteKit application.

Fixes:

- edit node_modules/web-translate/src/translate-franciscop/index.js
  and comment out this line:

  ```js
  global.fetch = require('node-fetch');
  ```

To run this:

- `npm install`
- `npm run dev`
- browse localhost:3000
