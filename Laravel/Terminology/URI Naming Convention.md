**URIs as resources as nouns:**
* One of the most recognizable characteristics is the predominant use of nouns in URIs.
* URIs should not indicate any kind of functionality. 
* Instead, should allow you to manipulate a resource.

```
Example: /users/{id} instead of /getUser
```

**Forward slashes for hierarchy:**
* Forward slashes are conventionally used to show the hierarchy between individual resources and collections

```
Example: /users/{id}/address clearly falls under the /users/{id} resource which falls under the /users collection
```