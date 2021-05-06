<template>
  <div id="app">
    <Input 
      name='Usuario' 
      :rules="{ required: true, min: 5 }"
      :value="usuario.value"
      @update="update"
    />
    {{ usuario }}
    <Input 
      name='Password' 
      :rules="{ required: true, min: 10 }"
      :value="password.value"
      @update="update"
    />
    {{ password }}
    <Button 
      color='white'
      background='darkslateblue'
      :disabled="valid"
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
      valid: false,
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
      this[payload.name.toLowerCase()].value = payload.value
    }
  }
}
</script>

<style>
  body {
    font-family: Arial;
  }
</style>
