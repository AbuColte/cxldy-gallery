<script>
import pathconfig from './pathconfig.json'
export default {
    data() {
        return {
            data: pathconfig
        }
    },
    props: ['title']
}
</script>
<template>
<div  class="flex justify-center flex-col items-center gap-4 w-[60vw]">
    
    <div id="main" class="text-[7vw] backdrop-blur-[2px] border-2 border-[red] p-4 rounded-lg text-center" style="text-shadow: red 0px 0px 15px;">Welcome</div>
    <!-- <div class="text-white active:scale-100 hover:scale-105 transition-all 1s hover:grayscale-0 grayscale hover:cursor-pointer" v-for="(i, index) in title">
        <div class="text-[5vw] font-mono text-[white] flex justify-center absolute m-2 font-bold bg-[red] p-2 h-fit rounded-lg">{{ i.title }}</div>
        <img :src="i.src" alt="" class="  transition-all 1s border-2  border-[red] rounded-lg" >
    </div> -->
</div>
    <div class="text-[5vw] backdrop-blur-[2px] border-2 border-[red] p-4 rounded-lg" style="text-shadow: red 0px 0px 15px;">Check out my Art.</div>
    <img id="main" :src="data.components.GraphicsCard.props.title[1].src" class="w-[90vw] rounded-[20px] border-2 border-[red] hover:scale-105 transition-all 1s" alt="">
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
  #main {
    width: 60vw;
  }
}

::selection {
  background-color: red;
  color: black;
}

</style>