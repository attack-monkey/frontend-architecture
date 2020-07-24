# frontend-architecture-2020
Building Frontend Applications in 2020

## Introduction

In 2020 there are a vast number of ways to build applications.
To undertake a Greenfields project, there are many factors to consider.

Not too long ago the dominant way was to use a server-side language to generate the frontend. Javascript were badly written add-ons at the bottom of a JSP (Java) / ASP / PHP / etc. Jquery was the dominant Javascript variant because it short-handed many of Javascript's DOM related functions. Javascript and Jquery were often written in a very imperative way, because it's prototype based object system was very different than the class based system that Java and C# were written in. Also Javascript and JQuery tended to be blobs tacked on to the bottom of a html doc, targeting DOM elements above and instructing them what to do.

**Fast-forward to 2020**

Javascript is modular and can run both client and server-side. Type-safety is easy with Typescript; a Javascript Superset. There are a large amount of Javascript frameworks to build the front-end, without any help from the server. The rise of the JAM (Javascript / API / Markup) Stack makes the front-end extremely fast to develop, build, deploy, load, etc. Javascript is now rarely written in the poor imperative manner of error-prone days past. The language itself now has classes, making it easier to be written in an Object Oriented way. The likes of Angular framework embrace this. The rise of React + Redux has also shown how functional javascript can be used to write much cleaner, less error prone code than that of it's object-oriented counter-parts. Since the rise of frameworks like Vue and React, the enjoyment and adoption of Angular has greatly reduced.

Modern languages are all now embracing more functional paradigms, including JVM based Scala and Kotlin, as well as .Net based F#, and low level languages like Rust and Go. Whle functional languages are able to generate cleaner, less error-prone code, there is a massive object-oriented community out there - stuck in their ways - so many languages are hybrids between functional and object oriented.

To complicate things further; most languages can now be transpiled to Javascript, making anything potentially a candidate for writing both back and front-end code.

With all the transpiling that is possible; these transpiled languages often lack the rich dynanism of Javascript and in particular it's ability to lazy-load more code at the right time - reducing initial load time and proving a faster Frontend experience.

My preferred stack in 2020 takes into account the following principles;

## Principles

- Fast
  - To develop ( Framework, Easy to learn, Code completion, Clean Pure Code, State Management )
  - To build ( Code Bundling, Tree-shaking, Minification, CSS Post Processing, CI/CD )
  - To deploy
  - To load ( CDN, Local Cache, Minified Code, Static, JAM Stack, Prerendered, Lazy Loading & Eager Loading )
  - To use ( Single Page Application, Emphasis on beautiful and consistent UI/UX )
  - To refactor ( Clean Pure Code, Separation of Concerns )
  - For clients to update ( CMS )
  
- Safe
  - Secure (Static Analysis of Dependencies, Scanable)
  - It should be hard to introduce errors and vulnerabilities (Type-safety, Type-certainty, Purity, Linting, Static Analysis, Unit Tests) 
  
- Scalable
  - 1 codebase to many clients
  - PaaS
  - Config driven
  - Themeable
  - Feature Toggles & Component Feature Toggles
  - Ability to update config to update code
  - Multi-zone ( Multiple SPAs deployed as one Site )
  - Shared Assets / Asset overrides
  - Responsive
  - Progressive Web App (Blurring the line between site and mobile app)

## Stack of Choice
  
- Language: **[Typescript](https://www.typescriptlang.org/)** - A superset of javascript that adds type-safety to the language
- Framework: **[Next.js](https://nextjs.org/)** - React based framework with emphasis on speed to write, build, deploy, load, use, etc. )
- State Management: **[HypeReduce](https://www.npmjs.com/package/hypereduce) \*** or Redux - State management with emphasis on clean, pure code
- Paradigm: **[Flat Code Guide](https://github.com/attack-monkey/flat-code-guide)** - Principles, rules, and minimal libraries for writing clean, pure, untangled code \*
- Testing: **[Jest](https://jestjs.io/)** or Mocha - Unit Tests
- Editor: **[VS Code](https://code.visualstudio.com/)** - Works amazingly with Typescript, including live collaboration, code completion, linting, formating, etc.
- Linting: **[ES Lint](https://eslint.org/)**, Typescript Rule Configuration
- CMS: **[Butter CMS](https://buttercms.com/)** or another Headless CMS that works well with Next.js
- UI Framework: **[Bootstrap](https://getbootstrap.com/)** **TODO: Review this**

\* HypeReduce and  \* Flat are tools created by me.

**HypeReduce** is a much leaner, event driven varient of Redux - removing a huge amount of boilerplate, and emphasising code re-use.

**Flat** is a guide plus a small set of libraries for writing flat, clean, pure, untangled javascript and typescript.

## Software Archtecture

Just as important as the tech-stack are the paradigms and architecture underpinning the software. Using the Flat Code guide as a starting point means that code is written in a clean, untangled way, with an emphasis on functional principles (without some of the more complex functional overhead). Using this as a starting point means that code will be less error-prone, and easier to refactor when change is required. Tying this in with React Functional Components and HypeReduce State Management provides the basis for an extremely clean application.

Using React with HypeReduce uses a clean one-way data flow using [Model View Update](https://thomasbandt.com/model-view-update) architecture pattern. The underpinning State ( Model ) is updated, which then rerenders the view where necesarry. It's pretty much that simple.

Sitting above this is how to utilise something like Next.js **correctly** from the start to enable Multi-tenanted / Lightweight code. In a proof of concept, I have used environment variables in a simple file that would ship with the environment to enable different builds for different clients. This system runs at compile time and doesn't add to runtime overhead. Unlike config in legacy apps, these Environment Variables are very few, and connect to richer type-safe config within the app (still not adding to runtime overhead).
