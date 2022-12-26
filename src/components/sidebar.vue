<template>
  <div class="mt-6 ml-8">
    <v-card
      width="300"
      tile
      outlined
      class="py-0 mt"
    >
      <v-card-title class="text-subtitle-1 font-weight-bold">
        FILTER
      </v-card-title>
    </v-card>

    <v-card
      width="300"
      tile
      outlined
      class="py-0 mt"
    >
      <v-card-title>
        <v-expansion-panels>
          <v-expansion-panel
            v-for="filter in filters"
            :key="filter.id"
            width="300"
            tile
            outlined
            elevation="0"
          >
            <v-expansion-panel-header class="font-weight-regular">
              {{filter.title}}
            </v-expansion-panel-header>
            <v-expansion-panel-content>
             <div
             v-for="choice in filter.choices"
             :key="choice.id"
              >
              <v-checkbox
                
                :label="`${choice}`"
              >

              </v-checkbox>
             </div>
              
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-card-title>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "Sidebar",

  data: () => ({
    filters: [
      {
        id: 1,
        title: "Category",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 2,
        title: "Price",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 3,
        title: "Discount",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 4,
        title: "Colour",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 5,
        title: "Size",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 6,
        title: "Neck Type",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 7,
        title: "Sleeve",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 8,
        title: "Occasion",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 9,
        title: "Length",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 10,
        title: "Fastening/Closure",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 11,
        title: "Pattern",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 12,
        title: "Ornamentation",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 13,
        title: "Fabric Family",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
      {
        id: 14,
        title: "Closure",
        choices: ["Kurtas", "Sets & Dresses", "Tops"]
      },
    ]
  })
}
</script>

<style scoped>

</style>