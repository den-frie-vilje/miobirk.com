# Vendored JavaScript

three.js r178 (`three.module.min.js` and its internal dependency
`three.core.min.js`), MIT licence, from the official npm build via
cdn.jsdelivr.net. Used by the Overlappet mockup for the hero's
liquid-chrome m. Production should vendor three via the package manager
(`pnpm add three`) rather than these copies; they exist so the mockup is
a plain static file. Note the pair must be served over HTTP: ES module
imports are blocked on file:// URLs.
