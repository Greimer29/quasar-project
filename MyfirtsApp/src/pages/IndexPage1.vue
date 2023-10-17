<template>
  hola
  <CardComponent v-for="(item,index) in items" :key="index" :title="item.title" :subtitle="item.subtitle" :text="item.text"/>
</template>

<script>
import { defineComponent, ref } from 'vue'
import CardComponent from 'src/components/CardComponent.vue';
export default defineComponent({
  name: 'IndexPage1',
  components:{
    CardComponent
  },
  setup(){
    const items = ref([
      {
        title:'a',
        subtitle:'b',
        text:'c'
      },
      {
        title:'a',
        subtitle:'b',
        text:'c'
      },
      {
        title:'a',
        subtitle:'b',
        text:'c'
      }
    ])

    return{
      items
    }
  }
})
</script>
