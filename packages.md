# Admin Packages

* **mfactory:admin-base**

  Base package containing configuration API, auth and CRUD methods.

* **mfactory:admin-[iron,flow,react]-router**

  Integration with routers.

* **mfactory:admin-lte**

  Admin LTE blaze theme.

* **mfactory:admin-tabular**

  Generates views with aldeed:tabular.

# API example

Core components of meteor admin:

* **routes**
* **views**
* **sidebar**

Following code

```javascript
Admin.collections.add('posts');
```

Will create 3 routes and views (view all, view one, edit) and sidebar items. Created views and routes can be configured/added, e.g.

```javascript
Admin.collections.add('posts', {
  views: {
    // configure automatically generated view
    all: {
      template: 'mfAdminTabular',
      data: {
        sort: { createdAt: -1 }
      },
      sidebar: {
        label: 'View all posts'
      }
    }

    // create additional view
    awaitingApproval: {
      template: 'mfAdminTabular',
      data: {
        selector: { approved: false }
      },
      sidebar: {
        label: 'Awaiting approval',
        count: function () {
          return Posts.find({ approved: false }).count();
        }
      },
      route: {
        path: '/posts/not-approved'
      }
    }
  }
});
```
