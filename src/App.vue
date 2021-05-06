<template>
  <div id="app">
    <Input 
      name='Usuario' 
      :rules="{ required: true, min: 5 }"
    />
    <Input 
      name='Password' 
      :rules="{ required: true, min: 10 }"
    />
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
      valid: false
    }
  }
}
</script>

<style>
  body {
    font-family: Arial;
  }
</style>
