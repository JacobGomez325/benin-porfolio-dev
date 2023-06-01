<template>
  <div class="relative">
    <header class="bg-[#142146] py-6 ">
      <div class="md:container px-4 mx-auto">
        <TheNavbar @search="getSearch" />
        <div class="pt-5 pb-4">
          <h1 class="text-white text-5xl py-4 font-bold">Benin Portfolios</h1>
          <p class="pt-2 pb-8 font-semibold text-white text-2xl">Open source collection of Benin portfolios</p>
          <button class="border md:hidden block border-secondary bg-secondary  text-xl px-4 py-3 my-2 font-bold shadow rounded-md  hover:opacity-70 transition-all duration-200">Your portfolio</button>
          <button class="border border-secondary font-bold text-white text-xl px-4 py-3 rounded-md  hover:bg-secondary hover:text-black transition-all duration-200 ">Contribute on github</button>
        </div>
      </div>

    </header>

    <main id="top" class="bg-[#10172a] py-6">
      <div class="container px-4 mx-auto grid  md:grid-cols-content  grid-cols-1 gap-4">
        <div class="tags">
          <h1 class="text-2xl font-bold text-white py-3">Filter by</h1>
          <div class="flex flex-wrap ">

            <Tags
              v-for="(tag,index) in tags"
              :key="index"
              :tag="tag"
              :tags="tags"
              @changeTags="changeTag"
            />

          </div>
        </div>

        <div v-if="resultQuery.length === 0">
          <empty>Aucune données  !!!</empty>
        </div>
        <div v-else class="grid lg:grid-cols-2 grid-cols-1 gap-4">
          <Card
            v-for="(data,index) in resultQuery"
            :key="index"
            :name="data.name"
            :link="data.link"
            :link-slug="data.link_slug"
            :social="data.socials"
            :tags="data.tags"

          />
        </div>
      </div>
    </main>

    <div class="h[1px] w-full bg-[#1e293b] my-3"></div>
    <TheFooter />
    <nuxt-link to="#top" class="bg-secondary fixed right-10  bottom-3 p-2 rounded-full">
      <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" height="1.3em" width="1.3em" xmlns="http://www.w3.org/2000/svg"><desc></desc><path stroke="none" d="M0 0h24v24H0z" fill="none"></path><path d="M9 20v-8h-3.586a1 1 0 0 1 -.707 -1.707l6.586 -6.586a1 1 0 0 1 1.414 0l6.586 6.586a1 1 0 0 1 -.707 1.707h-3.586v8a1 1 0 0 1 -1 1h-4a1 1 0 0 1 -1 -1z"></path></svg>
    </nuxt-link>


  </div>
</template>

<script>
  import {datas} from '@/data/data.js'
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
        {name:'gamedev',isActive:false},
      ],
      datas,
      search:''
    }
  },
  computed: {

      resultQuery(){
        if(this.search){
          return this.datas.filter((item)=>{
            return this.search.toLowerCase().split(' ').every(v => item.name.toLowerCase().includes(v))
          })
        }else{
          return this.datas;
        }
      }

    },
  methods: {
    getSearch(data) {
      this.search = data
    },
    changeTag(data) {
      this.datas = data
    }


  },
}
</script>
<style scoped>

</style>
