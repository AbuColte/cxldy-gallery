<script>
export default {
    data() {
        return {
            textOpened: false
        }
    },
    methods: {
        openText() {
            this.textOpened =! this.textOpened
        },
        copyText () {
            var text = document.getElementsByTagName('pre')[0].innerHTML
            navigator.clipboard.writeText(text)
            console.log(text)
        }
    },
    props: ['']
}
</script>
<template>
<div  class="flex justify-center flex-row gap-4">
    <div id="main" class="scale-110 flex font-mono text-white flex-col backdrop-blur-[2px] m-4 p-4 rounded-lg border-2 border-[red]">
        <div class="text-[5vw] w-full flex justify-center ">Contacts</div>
        <div class=" text-[5vw] flex flex-row">email: <a href="mailto:zmb.danil0@gmail.com"><div class="hover:shadow-[inset_0px_-20px_red] active:shadow-[inset_0px_-15px_red] transition-all 1s hover:cursor-pointer">zmb.danil0@gmail.com</div></a></div>
        <div>
            <div class="text-[5vw]">pgpkey:</div>
        <pre id="pgpKey" :class="this.textOpened ? 'text-[2vw]' : 'text-[2vw] h-[200px] overflow-hidden'">
-----BEGIN PGP PUBLIC KEY BLOCK-----

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
5/lV1IjAS7/OGkA9jiI=
=y4M4
-----END PGP PUBLIC KEY BLOCK-----
</pre></div>
<div class="flex flex-row gap-4 flex-wrap border-t-2 border-[red]">
<div class="text-3xl hover:shadow-[inset_0px_-10px_red] w-fit active:shadow-[inset_0px_-5px_red] transition-all 1s hover:cursor-pointer" @click="openText">{{this.textOpened ? 'less' : 'more'}}</div>

<div class="text-3xl hover:shadow-[inset_0px_-10px_red] w-fit active:shadow-[inset_0px_-5px_red] transition-all 1s hover:cursor-pointer" @click="copyText">copy</div>    
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

::selection {
  background-color: red;
  color: black;
}

</style>