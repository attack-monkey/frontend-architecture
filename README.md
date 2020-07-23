# frontend-architecture-2020
A Review of Frontend Applications in 2020

## Introduction

In 2020 there are a vast number of ways to build applications.
To undertake a Greenfields project, there are many factors to consider...

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

## Stack
  
- Typescript - A superset of javascript that adds type-safety to the language
- Next.js - React based framework with emphasis on speed to write, build, deploy, load, use, etc. )
- HypeReduce \* or Redux - State management with emphasis on clean, pure code
- Flat Code Guide - Principles, rules, and minimal libraries for writing clean, pure, untangled code \*
- Jest or Mocha - Unit Tests
- VS Code - Works amazingly with Typescript, including live collaboration, code completion, linting, formating, etc.
- Linting - ES Lint, Typescript Rule Configuration

- Headless CMS??
