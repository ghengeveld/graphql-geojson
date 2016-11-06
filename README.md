# graphql-geojson
GraphQL schema object types for GeoJSON

## Installation

```bash
npm i -S graphql-geojson
```

or with Yarn:

```bash
yarn add graphql-geojson
```

## Usage

```js
import { GraphQLObjectType, GraphQLSchema } from 'graphql'
import { PointObject } from 'graphql-geojson'

export default new GraphQLSchema({
  query: new GraphQLObjectType({
    name: 'Query',
    fields: () => ({
      point: {
        type: PointObject,
        resolve: () => ({
          type: 'Point',
          coordinates: [-105.01621, 39.57422],
        }),
      },
    }),
  }),
})
```

Then you can query it like this:

```graphql
query {
  point {
    type
    coordinates
  }
}
```

## Demo

An example GraphQL server implementation is available here:
https://github.com/ghengeveld/graphql-geojson-demo
