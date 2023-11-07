<template>
  <div style=" margin: auto; width: 25%; margin-top:150px;">
  <q-input v-model="user" label="Usuario"/>
  <q-input type="password" v-model="password" label="Cotrasena"/>
  <q-btn class="q-mt-xl full-width" label="iniciar" color="positive" @click="validate"/>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import { useQuasar } from 'quasar'
import { useRouter } from 'vue-router'

const users = [
  {
    user: 'greimer',
    password: '1234'
  },
  {
    user: 'yohan',
    password: '5678'
  },
  {
    user: 'samuel',
    password: '9012'
  },
  {
    user: 'Carla',
    password: '4321'
  }
]

export default defineComponent({
  name:'LoginLayout',
  setup(){
    const $q = useQuasar()
    const router = useRouter()
    const user = ref('')
    const password= ref('')

    const validate = () => {
      if(user.value.trim() && password.value.trim()){
        const found = users.find(val => val.user === user.value && val.password === password.value)

        if(found){
          router.push('/menu')
        }else{
          $q.notify({
            message: 'Credenciales incorrectas',
            color:'negative',
            multiline:true,
            avatar: 'https://cdn.quasar.dev/img/boy-avatar.png'
          })
        }
      }else{
          $q.notify({
            message: 'Campos vacios',
            color:'negative',
            multiline:true,
            avatar: 'https://cdn.quasar.dev/img/boy-avatar.png'
          })
        }
    }
    return {
      user,
      password,
      validate
      }
  }

})

</script>
