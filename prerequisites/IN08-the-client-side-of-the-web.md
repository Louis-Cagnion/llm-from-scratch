# IN08. The client side of the web

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 3. Analysis, probability and algorithms | IN02 | IN15, ME03 |

## Why this module

The web chat application of the project is written in plain HTML, CSS and JavaScript, without any framework: streaming answers, rendering Markdown, displaying artifacts in a side panel, uploading images. The project's charts are drawn as hand-made SVG. This module teaches the browser side from the ground up.

## Objectives

After this module, you can build accessible, responsive web pages with HTML and CSS, make them interactive with JavaScript, talk to a server with `fetch` and streams, and draw charts with SVG.

## Competences evaluated

1. Write semantic, valid HTML (structure, text, lists, links, images, forms, tables) and explain the DOM tree.
2. Style pages with CSS: selectors, specificity and cascade, box model, units, colors, typography, and custom properties (variables).
3. Lay out pages with flexbox and grid, and make them responsive (media queries, fluid sizes) without horizontal scrolling.
4. Write JavaScript with its types, functions, objects, arrays, classes, modules, and explain scope, closures and `this`.
5. Manipulate the DOM and handle events (delegation, default actions, keyboard).
6. Write asynchronous code with promises and `async`/`await`, call a server with `fetch`, and read a streamed response chunk by chunk.
7. Draw shapes, text and simple charts with SVG, and generate SVG from data.
8. Apply accessibility basics (semantic elements, labels, keyboard navigation, contrast) and check them.
9. Use the browser developer tools to debug layout, scripts and network requests.

## Notions, in learning order

1. **How the web works**: client and server, URLs, the browser's job.
2. **HTML**: document structure, semantic elements, forms, accessibility attributes.
3. **CSS fundamentals**: selectors, cascade, specificity, inheritance, box model, units, colors, fonts, custom properties.
4. **Layout**: normal flow, flexbox, grid, positioning, responsive design, media queries.
5. **JavaScript language**: values and types, functions, closures, objects and prototypes, classes, arrays and their methods, modules, errors.
6. **The DOM**: selecting, creating and modifying elements, events, event delegation.
7. **Asynchronous JavaScript**: the event loop, promises, `async`/`await`, `fetch`, readable streams, `EventSource` (first look).
8. **SVG**: coordinate system, shapes, paths, text, generating SVG from data.
9. **Accessibility and tooling**: accessible patterns, developer tools.

## Practice

- A personal page, then a responsive layout reproduced from a sketch.
- A to-do application in plain JavaScript with keyboard support.
- A page that streams text from a local test server and displays it as it arrives (the seed of the L47 web chat).
- A small library of SVG charts (line chart, bar chart) generated from data, reused for the experiment plots of the project.

## Evaluation format

One practical session, about 3 hours: build a small interactive, responsive and accessible page from a specification, including a streamed request and an SVG chart, plus questions on the cascade, the DOM and the event loop. Pass mark 100 %.

## References

- MDN Web Docs: *Learn web development* (HTML, CSS, JavaScript) and the SVG tutorial (free).
- *javascript.info* (free online tutorial).
