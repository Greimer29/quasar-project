<template>
  <table>
    <tr>
      <td>NOMBRE</td>
      <td>APELLIDO</td>
      <td>EDAD</td>
    </tr>
    <tr v-for="(item,index) in fila" :key="index">
      <td> {{ item.nombre }} </td>
      <td> {{ item.apellido }} </td>
      <td> {{ item.edad }} </td>
    </tr>
  </table>
</template>
<script>
import { defineComponent } from 'vue';
  export default defineComponent({
    name: 'TablaComponent',
    components:{},
    props:{
      fila:{
        type: Array,
        required: true
      }
    }

  })
</script>
<style>
th,td,table{
  max-width: 600px;
  max-height: 15px;
  border: 2px solid black ;
  border-collapse: collapse;
}
</style>
