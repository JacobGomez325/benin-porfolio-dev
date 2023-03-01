<template>
  <div >
    <header class="bg-[#142146] py-6 ">
      <div class="container mx-auto">
        <TheNavbar />
        <div class="pt-5 pb-4">
          <h1 class="text-white text-5xl py-4 font-bold">Benin Portfolios</h1>
          <p class="pt-2 pb-8 font-semibold text-white text-2xl">Open source collection of Benin portfolios</p>
          <button class="border border-secondary font-bold text-white text-xl px-4 py-3 rounded-md  hover:bg-secondary hover:text-black transition-all duration-200 ">Contribute on github</button>
        </div>
      </div>

    </header>
    <main id="top" class="bg-[#10172a] py-6">
      <div class="container mx-auto content gap-4">
        <div class="tags">
          <h1 class="text-2xl font-bold text-white py-3">Filter by</h1>
          <div class="flex flex-wrap ">

            <div v-for="(tag,index) in tags" :key="index" >
              <div
                :class="{'bg-secondary': tag.isActive===true,'border border-secondary hover:bg-secondary text-white  hover:text-black':tag.isActive===false}"
                class="flex space-x-3 items-center m-2 px-3 py-1 cursor-pointer  rounded-2xl transition-all duration-200 "
                @click="toogleTags(tag)">
                <span v-if="!tag.isActive" class="font-semibold  ">#</span>
                <span v-else class="block bg-black w-2 h-2 rounded-full "></span>
                <span  class=" font-semibold  "> {{ tag.name }} </span>
              </div>
            </div>

          </div>
        </div>
        <div class="grid grid-cols-2 gap-4">
          <div v-for="i in 30" :key="i" class="bg-[#1e293b] p-4 rounded-md shadow">
            <h2 class="text-2xl font-bold text-white py-2">Gomez jacob</h2>
            <p class="flex space-x-2 py-2">
              <span class="text-secondary"><svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 1024 1024" height="1.5em" width="1.5em" xmlns="http://www.w3.org/2000/svg"><path d="M574 665.4a8.03 8.03 0 0 0-11.3 0L446.5 781.6c-53.8 53.8-144.6 59.5-204 0-59.5-59.5-53.8-150.2 0-204l116.2-116.2c3.1-3.1 3.1-8.2 0-11.3l-39.8-39.8a8.03 8.03 0 0 0-11.3 0L191.4 526.5c-84.6 84.6-84.6 221.5 0 306s221.5 84.6 306 0l116.2-116.2c3.1-3.1 3.1-8.2 0-11.3L574 665.4zm258.6-474c-84.6-84.6-221.5-84.6-306 0L410.3 307.6a8.03 8.03 0 0 0 0 11.3l39.7 39.7c3.1 3.1 8.2 3.1 11.3 0l116.2-116.2c53.8-53.8 144.6-59.5 204 0 59.5 59.5 53.8 150.2 0 204L665.3 562.6a8.03 8.03 0 0 0 0 11.3l39.8 39.8c3.1 3.1 8.2 3.1 11.3 0l116.2-116.2c84.5-84.6 84.5-221.5 0-306.1zM610.1 372.3a8.03 8.03 0 0 0-11.3 0L372.3 598.7a8.03 8.03 0 0 0 0 11.3l39.6 39.6c3.1 3.1 8.2 3.1 11.3 0l226.4-226.4c3.1-3.1 3.1-8.2 0-11.3l-39.5-39.6z"></path></svg></span>
              <span class="text-white font-semibold">gojanda.dev.io</span>
            </p>
            <div class="flex flex-wrap">
              <div class="flex space-x-3 items-center border border-secondary text-white m-2 px-3 py-1 cursor-pointer  rounded-2xl transition-all duration-200 ">
                <span  class="block bg-white w-2 h-2 rounded-full "></span>
                <span  class=" font-semibold  "> frontend </span>
              </div>
              <div class="flex space-x-3 items-center border border-secondary text-white m-2 px-3 py-1 cursor-pointer  rounded-2xl transition-all duration-200 ">
                <span  class="block bg-white w-2 h-2 rounded-full "></span>
                <span  class=" font-semibold  "> backend </span>
              </div>
              <div class="flex space-x-3 items-center border border-secondary text-white m-2 px-3 py-1 cursor-pointer  rounded-2xl transition-all duration-200 ">
                <span  class="block bg-white w-2 h-2 rounded-full "></span>
                <span  class=" font-semibold  "> design </span>
              </div>
            </div>
          </div>

        </div>
      </div>
    </main>

    <div class="h[1px] w-full bg-[#1e293b] my-3"></div>

    <footer class="py-3 bg-[#10172a] ">
      <div class="container mx-auto  flex justify-between">
        <div class="text-2xl text-white font-semibold">
          &#9426; <span>{{ year }}</span> Benin Portfolios. All rights reserved
        </div>
        <div class="flex items-center space-x-6">
          <a href="#" class="text-secondary"><svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 16 16" height="2.2em" width="2.2em" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" clip-rule="evenodd" d="M7.976 0A7.977 7.977 0 0 0 0 7.976c0 3.522 2.3 6.507 5.431 7.584.392.049.538-.196.538-.392v-1.37c-2.201.49-2.69-1.076-2.69-1.076-.343-.93-.881-1.175-.881-1.175-.734-.489.048-.489.048-.489.783.049 1.224.832 1.224.832.734 1.223 1.859.88 2.3.685.048-.538.293-.88.489-1.076-1.762-.196-3.621-.881-3.621-3.964 0-.88.293-1.566.832-2.153-.05-.147-.343-.978.098-2.055 0 0 .685-.196 2.201.832.636-.196 1.322-.245 2.007-.245s1.37.098 2.006.245c1.517-1.027 2.202-.832 2.202-.832.44 1.077.146 1.908.097 2.104a3.16 3.16 0 0 1 .832 2.153c0 3.083-1.86 3.719-3.62 3.915.293.244.538.733.538 1.467v2.202c0 .196.146.44.538.392A7.984 7.984 0 0 0 16 7.976C15.951 3.572 12.38 0 7.976 0z"></path></svg></a>
          <nuxt-link to="#top" class="bg-secondary p-2 rounded-full">
            <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" height="1.3em" width="1.3em" xmlns="http://www.w3.org/2000/svg"><desc></desc><path stroke="none" d="M0 0h24v24H0z" fill="none"></path><path d="M9 20v-8h-3.586a1 1 0 0 1 -.707 -1.707l6.586 -6.586a1 1 0 0 1 1.414 0l6.586 6.586a1 1 0 0 1 -.707 1.707h-3.586v8a1 1 0 0 1 -1 1h-4a1 1 0 0 1 -1 -1z"></path></svg>
          </nuxt-link>
        </div>
      </div>

    </footer>

  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      tags:[
        {name:'All tags',isActive:true},
        {name:'frontend',isActive:false},
        {name:'backend',isActive:false},
        {name:'design',isActive:false},
        {name:'mobile',isActive:false},
        {name:'devops',isActive:false},
        {name:'web3',isActive:false},
        {name:'data',isActive:false},
        {name:'cybersecurity',isActive:false},
        {name:'machine learning',isActive:false},
      ]


    }
  },
  computed: {
      year() {
        return new Date().getFullYear()
      },
    },
  methods: {
    toogleTags(element) {
      this.tags.forEach(tag => {
        if(tag.isActive === true) {
          tag.isActive = false
          element.isActive = true
        }
      })
    }
  },
}
</script>
<style scoped>
.content {
  display: grid;
  grid-template-columns: 4fr 8fr;
}
</style>
