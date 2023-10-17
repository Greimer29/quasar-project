<template>
  <div class="q-pa-md" style="max-width: 700px;">
    <q-table :columns="columnas" :rows="filas" row-key="name">
      <template #body-cell-name="props">
        <q-td :props="props" class="text-italic text-purple">
          {{ props.value }}
        </q-td>
      </template>
      <template #body-cell-opciones="props">
        <q-td :props="props">
          <q-btn
            flat
            color="primary"
            :label="props.row.name"
            @click="copyToClipboard(props.value)"
          />
        </q-td>
      </template>
    </q-table>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
const columnas = ref([
  {
    name: 'nombre',
    align: 'center',
    label: 'Nombre',
    field: 'name',
  },
  {
    name: 'apellido',
    align: 'center',
    label: 'Apellido',
    field: 'lastname',
  },
  {
    name: 'edad',
    align: 'center',
    label: 'Edad',
    field: 'age',
  },
  {
    name: 'opciones',
    label:'opciones',
    field: val => `${val}`
  }
])

const filas = ref([
  {
    name: 'Greimer',
    lastname: 'Perez',
    age: 22
  },
  {
    name: 'Daira',
    lastname: 'Fermin',
    age: 19,

  }
])
export default defineComponent({
  setup(){
    return{
      columnas,
      filas
    }
  }
})
</script>
