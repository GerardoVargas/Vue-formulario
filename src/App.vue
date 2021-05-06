<template>
  <div id="app">
    <Button 
      color='white'
      background='darkslateblue'
      :disabled="valid"
    />
  </div>
</template>

<script>
import Button from './components/Button.vue'

export default {
  name: 'App',
  components: {
    Button
  },
  data(){
    return {
      valid: false
    }
  }
}
</script>

<style>

</style>
