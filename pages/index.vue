<template>
  <main>
    <h1>Home</h1>
    <button v-on:click="getShowcases">Showcases</button>
    <pre>{{ showcases }}</pre>
  </main>
</template>

<script>
export default {
  methods: {
    //first method
    async getShowcases () {
      this.showcases = await this.$strapi.$showcases.find([['plugins.slug', 'vue-routeur'], ['plugins.slug', 'vue-meta']])
      //test
    },
    //second method
    /* async getShowcases() {
      this.showcases = await this.$strapi.$showcases.find({ 'plugins.slug': ['vue-routeur', 'vue-meta'] })
    },*/
  },
  data () {
    return {
      showcases: []
    }
  }
}
</script>