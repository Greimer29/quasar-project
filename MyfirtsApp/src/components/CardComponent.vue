<template>
  <q-card class="my-card text white" style="background: radial-gradient(circle, #a3a2ff 0%, #014a88 100%)">
    <q-card-section>
      <div class="text-h6">{{ title }}</div>
      <div class="text-subtitle2">{{ subtitle }}</div>
    </q-card-section>
    <q-card-sextion class="q-pt-none">
      {{ text }}
    </q-card-sextion>
  </q-card>
</template>

<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "CardComponent",
  props: {
    title:{
      type: String,
      required: true
    },
    subtitle:{
      type: String,
      required: true
    },
    text:{
      type: String,
      required: true
    }
  }
})
</script>
