<template>
  <div
    class="q-pa-md row justify-center"
    style="max-width:400px ; background-image: linear-gradient(rgba(46, 43, 221, 0.788),rgb(0, 0, 255));"
  >

    <div style="width: 100%; max-width: 400px">
      <div v-for="(mensaje,index) in messages" :key="index" >
        <q-chat-message :text="[mensaje.text]" :sent="mensaje.type"/>
        {{ console.log(mensaje.type) }}
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "ChatComponent",
  props:{
    messages:{
      type: Array
    },
    type:{
      type:Boolean
    }
  },
  setup() {

    return {
    }
  }
})
</script>
