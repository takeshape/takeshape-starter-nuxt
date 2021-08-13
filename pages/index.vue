<template>
  <div>
    <h1>Products:</h1>
    <div v-if="getProductList">          
      <ul>
        <li v-for="product in getProductList.items" :key="product._id">
          {{ product.name }}: {{ product.price }}
        </li>
      </ul>
    </div>
    <div v-else>
      Testing...
    </div>
  </div>
</template>

<script>
import getProductList from '../apollo/queries/getProductList.gql'
export default {
    apollo: {
      getProductList: {
        query: getProductList
      }
    }
  }
</script>
