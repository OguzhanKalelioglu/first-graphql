<template>
  <div>
    <div v-for="item in posts.data" :key="item.id">
      <pre
        >       {{ item.attributes.Header }}
                {{ item.attributes.creator }}
                {{item.attributes.customers.data[0].attributes.CustomerName}}
            </pre
      >
    </div>
  </div>
</template>

<script>
import { gql } from "graphql-tag";

export default {
  apollo: {
    posts: gql`
      query getPosts {
        posts {
          data {
            id
            attributes {
              Header
              creator
              customers {
                data {
                  attributes {
                    CustomerName
                    Status
                  }
                }
              }
            }
          }
        }
      }
    `,
  },
};
</script>
