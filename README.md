# Mollo Creator

Version 0.1.0 alpha

Mollo Creator is my dream of a easy-to-use Drupal admin interface for Content Creators. The goal is a desktop-app-like
tool for Content Creators. I am going to integrate and unify all the different frontends from my Drupal Modules in this
one. R.I.P jQuery and CKE. TypeScript and Vue is coming.

This is my second attempt to implement this idea. The first one I started three years ago and was based on Angular 5 and PrimeFaces.

This Project is not ready to use, but in early developing.
Details at ROADMAP.md

## Mollo Creator

- Admin Interface for Content Creators.
- It will NOT be a Layout Designer.
- https://github.com/oliversteiner/mollo-creator

### Features for Drupal Devs

- Add every Entity Type to Creator Gui via your_module.creator.yml and graphQL schema
- add own Widgets for Creator via vue components
- A View Display who syncs with the Creator List Panel
- A Display mode who syncs with the Creator Edit Panel

### Features for Content Creators

- a fast and clear admin interface for all your content.
- a standalone app. Edit your content in the app, preview in the browser.
- Local Storage for offline editing and faster lists on large datasets

### Technics

- graphQL
- Vue 3 / Typescript
- Quasar
- TipTap Wysiwyg Creator (or for beginning simply the one from Quasar)
- Electron

### Dependencies

- mollo_basic
- mollo_utils
- drupal/graphql
- mollo_creator_drupal

### Resources

Mollo Creator Drupal Module

- https://github.com/oliversteiner/mollo-creator-drupal

Generates Typescript type definitions for certain entities

- https://github.com/hoppinger/ts_generator

Drupal GraphQL

- https://www.drupal.org/project/graphql

Quasar

- https://quasar.dev/

Security

- https://carvesystems.com/news/the-5-most-common-graphql-security-vulnerabilities/

Graphql server authentication with JWT

- https://dev.to/ahmdtalat/graphql-server-authentication-with-jwt-3mdi

TipTap

- https://tiptap.dev/
- https://github.com/donotebase/quasar-tiptap

Drupal Admin UI (react)
https://github.com/jsdrupal/drupal-admin-ui

Other

- https://www.drupal.org/about/strategic-initiatives/admin-ui-js
- https://www.lullabot.com/articles/drupal-javascript-initiative-the-road-to-a-modern-administration-ui
- https://www.drupal.org/project/ideas/issues/3017785



