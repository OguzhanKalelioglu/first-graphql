<template>
    <div>
        <div v-for="item in posts.data" :key="item.id">
            <pre>{{item.attributes.Header}}</pre>
            <pre>{{item.attributes.creator}}</pre>
        </div>
    </div>
</template>

<script>
import { gql } from 'graphql-tag'

export default {
    apollo : {
        posts : gql `
       query getPosts{
            posts {
         data {
         id
         attributes {
        Header
        creator
      }
    }
  }
}`
    }
}
</script>
