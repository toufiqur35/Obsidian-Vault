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
Example: /users/{id}/address  clearly falls under the  /users/{id}  resource which falls under the  /users  collection
```

**Punctuation for lists:**
* When there is no hierarchical relationship (such as in lists), punctuation marks such as the semicolon, or, more frequently, the comma should be used.

```
Example: /users/{id}/  to access multiple user resource
```

**Query parameters where necessary:**
* In order to sort or filter a collection, a REST API should allow query parameters to be passed in the URI.

```
Example: /users?location=USA  to find all users living in the united states
```

**Lowercase letters and dashes:**
* By convention, resource names should use exclusively lowercase letters. Similarly, dashes (-) are conventionally used in place of underscores (_).

```
Example: /users/{id}/pending-order  instead of /users/{id}/Pending_Order
```

**No file extensions**
* Leave file extensions (such as .xml) out of your URIs. We’re sorry to say it, but they ’re ugly and add length to URIs. If you need to specify the format of the body, instead use the Content-Type header

```
Example: /users/{id}/pending-order  instead of /users/{id}/pending-order.xml
```

**No trailing forward slash**
* Similarly, in the interests of keeping URIs clean, do not add a trailing forward slash to the end of URIs.

```
Example: /users/{id}/pending-order  instead of /users/{id}/pending-order/
```