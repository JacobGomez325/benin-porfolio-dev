<template>
  <div>
    <div
      :class="{
        'bg-secondary': tag.isActive === true,
        'border border-secondary hover:bg-secondary text-white  hover:text-black':tag.isActive === false,}"
      class="flex xl:space-x-3 space-x-2 items-center m-2 px-3 py-1 cursor-pointer rounded-2xl transition-all duration-200"
      @click="toogleTags(tag)"
    >
      <span v-if="!tag.isActive" class="font-semibold">#</span>
      <span v-else class="block bg-black w-2 h-2 rounded-full"></span>
      <span class="font-semibold"> {{ tag.name }} </span>
    </div>
  </div>
</template>

<script>
  import {datas} from '@/data/data.js'

  export default {
    name: 'ComponentTags',
    props: {
      tag: {
        type: Object,
        required: true,
      },
      tags:{
        type:Array,
        required: true
      }
    },
    methods: {
      filtre(tag) {
        if(datas) {
          const dataTags = []
          if(tag !=='All tags') {
            datas.forEach((item) => {
              if(item.tags.includes(tag) ) {
                dataTags.push(item)
              }
            })
            this.$emit('changeTags', dataTags)
          }else {
            this.$emit('changeTags', datas)
          }
        }
      },
      toogleTags(element) {
        this.tags.forEach(tag => {
          if(tag.isActive === true) {
            tag.isActive = false
            element.isActive = true
            this.filtre(element.name)
          }
        })
      },
    },
  }
</script>

<style lang="scss" scoped></style>
