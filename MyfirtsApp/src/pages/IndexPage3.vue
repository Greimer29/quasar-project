<template>
  <q-page class="display-flex text-center flex">
    <div class="q-pa-md">
      <q-form class="q-gutter-md">
        <q-input v-model="mensaje" filled label="text"/>
        <q-btn label="Enviar" color="primary" icon="plane" @click="enviar" />
        <q-btn label="Recibir" color="secondary" icon="plane" @click="recibir" />
      </q-form>
    </div>
    <div>
      <ChatComponent :messages="mensajes" />
    </div>
  </q-page>
</template>

<script>
import ChatComponent from "src/components/ChatComponent.vue";
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "IndexPage3",
  components:{
    ChatComponent
  },
  setup() {
    const mensaje = ref('')
    const mensajes = ref([])

    const enviar =()=>{
      mensajes.value.push({text:mensaje.value,type:true})
    }
    const recibir =()=>{
      mensajes.value.push({text:mensaje.value,type:false})
    }

    return {
      mensajes,
      mensaje,
      enviar,
      recibir
    }
  }
})
</script>
