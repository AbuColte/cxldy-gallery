<script>
import pathconfig from './pathconfig.json'
export default {
    data() {
      return {
        data : pathconfig
      }
    },
    props: ['title']
};
</script>
<template>
    <div class=" z-50 font-mono flex flex-wrap backdrop-blur-[2.5px] gap-4 text-white p-4 text-2xl rounded-2xl border-[red] border-2 m-4 sticky top-5 ">
      <div v-for="(i, index) in title" class="transition-all 1s hover:cursor-pointer hover:shadow-[inset_0px_-10px_red] active:shadow-[inset_0px_-5px_red] " >{{ i }}</div>
      <div class="shadow-[inset_0px_-10px_red]">cxldygallery</div>
    </div>
</template>