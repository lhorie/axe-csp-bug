# React-axe CSP bug demo

### Codebase description

This repo contains a vanilla React app created via `create-react-app`

It has two modifications:

- The react-axe library is loaded in `src/index.js:7` (`require('react-axe');`)
- Content Security Policy is modified in `public/index.html:5` (`<meta http-equiv="Content-Security-Policy" content="script-src 'self'">`)

### Expected

The app should run

### Actual

There's a runtime error: `Uncaught EvalError: Refused to evaluate a string as JavaScript because 'unsafe-eval' is not an allowed source of script in the following Content Security Policy directive: "script-src 'self'".`

The error does not appear if the react-axe library is not loaded.