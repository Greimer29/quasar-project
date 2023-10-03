<template>
  <q-page class="display-flex text-center flex" >
<!--     <div class="q-pa-md" style="max-width: 400px">
      <q-form class="q-gutter-md">
        <q-input filled v-model="name" label="Nombre" />

        <q-input filled v-model="apellido" label="Apellido" />

        <div class="flex flex-center">
          <q-btn label="+" type="submit" color="primary" @click="plus" />
          <span class="q-pa-md"> {{ edad }} </span>
          <q-btn label="-" type="reset" color="red" @click="rest" />
        </div>

        <div class="q-pa-md flex flex-center">
          <q-btn label="Validar" color="primary" @click="validar" />
        </div>
      </q-form>
    </div>-->

    <!--<div class="q-pa-md q-gutter-sm" filled>
      <q-input v-model="nameA" label="Nombre" filled/>
      <q-btn color="secondary" label="Guardar de ultimo" @click="save"/>
      <q-btn color="red" label="eliminar ultimo" @click="borrar"/>
      <q-btn color="blue" label="Guardar de Primero" @click="savePri"/>
      <q-btn color="orange" label="Eliminar Primero" @click="borrarPri"/>
    <div>
      <ol>
        <div >
          <li v-for="(items,index) in nombres" :key="index" class="q-pa-md q-gutter-sm">
            {{ items }}
          <q-btn margin-left="50px" color="red" label="eliminar" @click="borrarUni(Key)"/>
          </li>
        </div>
      </ol>
    </div>
    </div>-->
    <div class="q-pa-md" style="max-width: 4e500px;">
      <q-form class="q-gutter-md">
        <q-input v-model="name" label="Nombre" filled/>
        <q-input v-model="lastname" label="Apellido" filled/>
        <q-input v-model="age" label="Edad" filled/>
        <q-btn color="green" label="Guardar" @click="save"/>
      </q-form>
    </div>
    <div class="q-pa-md" style="max-width: 400px;">
    <table>
      <tr>
        <th>Nombre</th>
        <th>Apellido</th>
        <th>Edad</th>
        <th>Opciones</th>
      </tr>
      <tr v-for="(item,index) in estudents" :key="index">
        <td>{{ item.name }}</td>
        <td>{{ item.lastname }}</td>
        <td>{{ item.age }}</td>
        <td>
          <q-btn icon="delete" color="red" rounded style="width: 40px;" @click="borrar(index)"/>
          <q-btn icon="update" color="blue" rounded style="width: 40px;" @click="upto(index)"/>
        </td>
      </tr>
    </table>
  </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "IndexPage",
  setup() {
    const name = ref()
    const lastname = ref()
    const age = ref()

    const opciones = ref(['delete'])

    const estudents = ref([
      {
        name: 'Daira',
        lastname: 'Fermin',
        age: 19
      },
      {
        name: 'Carla',
        lastname: 'Carrillo',
        age: 23
      },
      {
        name: 'Deiver',
        lastname: 'nomelose',
        age: 19
      }
    ])

    const save = () => {
      estudents.value.push({
        name: name.value,
        lastname: lastname.value,
        age: age.value
      })
      onReset();
    }

    const borrar = (index) => {
      estudents.value.splice(index,1)
    }
    const onReset = () => {
      name.value = null
      lastname.value = null
      age.value = null
    }
    const upto = (index) => {
      name.value = estudents.value[index].name
      lastname.value = estudents.value[index].lastname
      age.value = estudents.value[index].age
    }

    /*
   const edad = ref(18);
    const name = ref("");
    const apellido = ref("");

    const nameA = ref("");
    const nombres = ref([]);

    const save = () => {
      nombres.value.push(nameA.value)
    }
    const borrar = () => {
      nombres.value.pop()
    }
    const borrarUni = (key) => {
      nombres.value.slice()
      console.log(splice());
    }
    const borrarPri = () => {
      nombres.value.shift(nameA.value)
    }
    const savePri = () => {
      nombres.value.unshift(nameA.value)
    }

    const validar = () => {
      console.log(name.value);
      if (name.value === "" || apellido.value === "") {
        alert("Los campos estan vacios");
      } else {
        alert("Felicidades");
      }
    };

    const plus = () => {
      edad.value = edad.value + 1;
    };

    const rest = () => {
      edad.value = edad.value - 1;
    };
    */

    return {
      /*edad,
      name,
      apellido,
      validar,
      rest,
      plus,
      nameA,
      nombres,
      save,
      borrar,
      savePri,
      borrarPri,
      borrarUni*/
      estudents,
      save,
      name,
      lastname,
      age,
      opciones,
      borrar,
      onReset,
      upto
    };
  },
});
</script>

<style>
  table, th, td {
    border : 1px solid black;
    border-collapse: collapse;
    padding: 2px;
  }
</style>
