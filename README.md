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

