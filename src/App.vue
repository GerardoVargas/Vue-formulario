<template>
  <div id="app">
    <form class="form" @submit.prevent="send">
      <Input 
        name='Usuario' 
        :rules="{ required: true, min: 5 }"
        :value="usuario.value"
        @update="update"
        typeInput="text"
      />
      <Input 
        name='Password' 
        :rules="{ required: true, min: 10 }"
        :value="password.value"
        @update="update"
        typeInput="password"
      />
      <Button 
        color='white'
        background='darkslateblue'
        :disabled="!valid"
      />
    </form>
  </div>
</template>

<script>
import Button from './components/Button.vue'
import Input from './components/Input.vue'

export default {
  name: 'App',
  components: {
    Button,
    Input
  },
  data(){
    return {
      usuario: {
        value: '',
        valid: false
      },
      password: {
        value: '',
        valid: false
      }
    }
  },
  methods: {
    update(payload){
      this[payload.name.toLowerCase()] = {
        value: payload.value,
        valid: payload.valid
      }
    },
    send(){
      console.log('Enviando');
    }
  },
  computed: {
    valid(){
      return this.usuario.valid && this.password.valid
    }
  }
}
</script>

<style>
  body {
    font-family: Arial;
  }

  .form {
    max-width: 400px;
    width: 50%;
  }
</style>
