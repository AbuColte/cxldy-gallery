<script>
import navbar from './navbar.vue'
import GraphicsCard from './GraphicsCard.vue'
import pathconfig from './pathconfig.json'
export default {
  data() {
    return {
        fullImageClass: 'w-[90vw]',
        currentIndex: 0,
        data : pathconfig
    }
  },
  props : ['imgSrc'],
  methods: {
    changeNextIndex() {
        this.currentIndex++
    },
    changePrevIndex() {
        this.currentIndex--
    }
  },
  components: {
    navbar,
    GraphicsCard
  }
}
</script>
<template>
    <div id="main" class="flex flex-col items-center flex-wrap m-4 font-mono text-white ">      
        <div class="flex justify-center gap-4 flex-col items-center">
            
            <div id="container" v-for="(i, index) in data.components.MediaDisplay.props.images" class="flex flex-col items-center gap-2 h-auto w-[70vw] justify-center">
                <div class="text-[4vw] " style="text-shadow: red 0px 0px 15px;">{{ data.components.MediaDisplay.props.images[index].title }}</div>
                <div class="flex flex-row items-center justify-center gap-2">
                    <div class="hover:shadow-[inset_0px_-10px_red] active:shadow-[inset_0px_-5px_red] transition-all 1s hover:cursor-pointer text-[4vw]" @click="data.components.MediaDisplay.props.images[index].cIndex != 0 ? data.components.MediaDisplay.props.images[index].cIndex-- : data.components.MediaDisplay.props.images[index].cIndex = data.components.MediaDisplay.props.images[index].src.length - 1">PREV</div>
                    <img 
                    class=" shadow-lg rounded-lg border-2 border-[red] transition-all 1s hover:scale-105 w-[100vw]" 
                    id="images" 
                    :src="data.components.MediaDisplay.props.images[index].src[data.components.MediaDisplay.props.images[index].cIndex]" 
                    v-if="!data.components.MediaDisplay.props.images[index].src[data.components.MediaDisplay.props.images[index].cIndex].includes('.mp4')" 
                    alt="">
 
                    <video 
                    id="images" 
                    class="rounded-lg border-2 border-[red] transition-all 1s hover:scale-105 w-100vw]" 
                    :src="data.components.MediaDisplay.props.images[index].src[data.components.MediaDisplay.props.images[index].cIndex]" 
                    v-if="data.components.MediaDisplay.props.images[index].src[data.components.MediaDisplay.props.images[index].cIndex].includes('.mp4') " controls></video>

                    <div 
                    class="hover:shadow-[inset_0px_-10px_red] active:shadow-[inset_0px_-5px_red] transition-all 1s hover:cursor-pointer text-[4vw]" 
                    @click="data.components.MediaDisplay.props.images[index].src.length - 1 != data.components.MediaDisplay.props.images[index].cIndex ? data.components.MediaDisplay.props.images[index].cIndex++ : data.components.MediaDisplay.props.images[index].cIndex = 0">NEXT</div>
                    </div>
            </div>
        </div>

    </div>
</template>
<style scoped>
@keyframes blur {
    from {filter: blur(10px);}
    to {filter: blur(0px)}
}

#main {
    animation: blur 1s ;
}

@media screen and (min-width: 600px) {
  #images {
    width: 40vw;
  }
  #container {
    width: 50vw;
  }
}

::selection {
  background-color: red;
  color: black;
}

</style>