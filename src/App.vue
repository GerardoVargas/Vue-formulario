<template>
  <div id="app">
    <Input 
      name='Usuario' 
      :rules="{ required: true, min: 5 }"
      :value="usuario.value"
      @update="update"
    />
    <Input 
      name='Password' 
      :rules="{ required: true, min: 10 }"
      :value="password.value"
      @update="update"
    />
    <Button 
      color='white'
      background='darkslateblue'
      :disabled="!valid"
    />
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
        value: 'user',
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
</style>
