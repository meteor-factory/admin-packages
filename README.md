# Admin Packages

## Both

### `admin-base`
Global: `Admin`

### `admin-utils`
Global: `Admin.utils`

Methods:
* `Admin.utils.isAdmin(userId)`

### `admin-users`
Creates user / converts user to admin when specified in:
* env variables
* settings
* configured with AdminConfig


### `admin-config`
Global: `Admin.config`

Methods:
* `Admin.config(configObj)` extends `Admin._config` which holds the json. Should probably be run in `startup` function
* `Admin.addRoute(routeObj)`
* ...

## Server

### `admin-methods`
Adds CRUD meteor methods:
* `admin.insert(collection, doc)`
* `admin.update(collection, docId, modifier)`
* `admin.remove(collection, docId)`

### `admin-publish`
Adds publish function for admins

* `admin.find(collection, query)`
* `admin.findOne(collection, query/docId)`

## Client

### `admin-client-blaze`
Add templates and blaze helpers.

Adds `$AdminUtils` as a helper.

# Package vs. Repo vs. Generator
It should be easy to modify your admin dashboard. The easiest is having direct access to the code.

User should start by 1) Cloning a repo with a working app 2) Using a generator (see mantra)

This repo should contains the packages, giving the dev easy access.

It could even be the case that almost everything is in repo, giving the dev fuller control.

# Schemas
Until a good solution for astronomy forms exists, we just support 1) No schemas 2) Collection 2

## No schemas
We attempt to automatically generate schemas for the user. [Work in progress](https://github.com/meteor-factory/admin-zero-config).

## Collection2
We generate forms via AutoForm

# Setup

## Minimal
```
meteor add admin-server
meteor add admin-client-blaze
```

Will generate AdminConfig automatically.

## Basic
```
meteor add admin-server
meteor add admin-client-blaze
```

```js
const configObj = {
  ...
};

Meteor.startup(() => {
  Admin.config(configObj)
})
```
