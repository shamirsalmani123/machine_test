<template>
  <div class="mt-6 mx-8">
    <v-row>
      <v-col
        cols="3"
        v-for="product in list"
        :key="product.id"
      >
        <v-card
          class="mx-auto"
          max-width="250"
          max-height="600"
          tile
          outlined
        >
          <v-img
            :src="product.image">
          </v-img>
          <v-card-subtitle class="subtitle">
            {{product.name}}
          </v-card-subtitle>
          <v-card-subtitle class="font-weight-black subtitle">
            Rs. {{product.price}}
          </v-card-subtitle> 
            
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
  export default {
    name: 'Home',
    props: {
      list: Array
    },

    components: {
    },
  }
</script>

<style scoped>
.subtitle{
  padding: 6px 0 4px 8px;
}
</style>
