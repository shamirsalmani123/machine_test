<template>
  <v-app>
    <div class="d-flex">
      <sidebar />
      <HomeView :list = list />
    </div>
    
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import axios from "axios";
import sidebar from './components/sidebar.vue';
import HomeView from "./views/HomeView.vue";

export default {
  name: 'App',
  components: {
    sidebar,
    HomeView
  },  

  data: () => ({
    list: [],
    page: 1
  }),

  methods: {

    // Get Initial Data
    async getData() {
      let result = await axios.get(`https://pim.wforwoman.com/pim/pimresponse.php/?service=category&store=1&url_key=top-wear-kurtas&page=${this.page}&count=20&sort_by=&sort_dir=desc&filter=`)

      const value = this.list.concat(result.data.result.products)
      this.list = value
    },

    // Get Next Set of Data
    async getNextData() {
      let next = await axios.get(`https://pim.wforwoman.com/pim/pimresponse.php/?service=category&store=1&url_key=top-wear-kurtas&page=${this.page}&count=20&sort_by=&sort_dir=desc&filter=`)

      this.list.push(next.data.results.products)
    },
    
    handleScroll() {
    if(window.scrollY + window.innerHeight >= document.body.scrollHeight - 50) {
      this.page++
        this.getData();
    }
  }
  },

  mounted(){
    // this.getNextPage();
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeMount() {
    this.getData();
  }
};
</script>
