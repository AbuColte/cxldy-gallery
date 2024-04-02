<script>
import navbar from './components/navbar.vue'
import GraphicsCard from './components/GraphicsCard.vue'
import Contacts from './components/Contacts.vue'
import pathconfig from './components/pathconfig.json'
import MediaDisplay from './components/MediaDisplay.vue'
export default {
  data() {
    return {
      data : pathconfig,
      ActiveComponent: 'Home'
    }
  },
  methods: {
    toggleComponent(comp) {
      this.ActiveComponent = comp
    }
  },
  components: {
    navbar,
    GraphicsCard,
    MediaDisplay,
    Contacts
  }
}
</script>

<template>
  <div class="flex flex-col items-center flex-wrap m-4 text-white font-mono justify-center gap-4" >
    <!-- <navbar :title="data.components.navbar.props.titles"/> -->

    <div class=" z-50 font-mono flex flex-wrap backdrop-blur-[2.5px] gap-4 text-white p-4 text-2xl rounded-2xl border-[red] border-2 m-4 sticky top-5 ">
      <div v-for="(i, index) in data.components.navbar.props.titles" class="transition-all 1s hover:cursor-pointer hover:shadow-[inset_0px_-10px_red] active:shadow-[inset_0px_-5px_red] " @click="toggleComponent(i)">{{ i }}</div>
      <div class="shadow-[inset_0px_-10px_red]">cxldygallery</div>
    </div>
    <GraphicsCard v-if="ActiveComponent == 'Home'" :title="data.components.GraphicsCard.props.title"/>
    <Contacts v-if="ActiveComponent == 'Contacts'"/>
    <MediaDisplay :img-src="data.components.MediaDisplay.props.images" v-if="ActiveComponent == 'Artworks'"/>
    <!-- <navbar :title="data.components.navbar.props.titles"/> -->
    <!-- <div class="text-[10vw] ">Welcome</div>
    <GraphicsCard :title="data.components.GraphicsCard.props.title"/> -->
    <!-- <MediaDisplay :img-src="data.components.MediaDisplay.props.images" /> -->
  </div>
</template> 

<style scoped>
::selection {
  background-color: red;
  color: black;
}
</style>
