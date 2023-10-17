<template>
  <q-page class="display-flex text-center flex" >
    <TablaComponent :fila="students" />
  </q-page>
</template>

<script>
import TablaComponent from "src/components/TablaComponent.vue";
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "IndexPage",
  components:{
    TablaComponent
},
  setup() {
    const students = ref([
      {nombre:'Samuel',apellido:'Gutierrez',edad:'19?'},
      {nombre:'Deiver',apellido:'pernia',edad:'20?'},
      {nombre:'Carla',apellido:'Carrillo',edad:'20?'}
    ])

    return {
      TablaComponent,
      students
    }
  }
})
</script>
