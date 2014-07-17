regard-query-client-node
========================

Node module for accessing Regard query engine

## Environment variables

`QUERY_USERNAME`
`QUERY_PASSWORD`

## API

The query client requires an organization and product.

```js
var QueryClient = new QueryClient(organization, product);
```

All of the following methods return promises.

### registerQuery: function (name, definition)

Register a query with the query engine. The name should be a GUID. The definition is the JSON query definition, eg

```json
{
   "verb":"CountUniqueValues",
   "key":"user-id",
   "name":"value",
   "applies-to":{
      "verb":"AllEvents",
      "applies-to":{

      }
   }
}
```

### runQuery: function (queryName)

Run a query using the query GUID. Returns JSON with a `Results` property.

### deleteData: function (userId)

Deletes user data for the provided user id.

### getEventsForUser: function (userId)

Retrieves events for the provided user id. Returns JSON.
