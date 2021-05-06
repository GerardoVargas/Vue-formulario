<template>
 <div class='input-wrapper'>
   <div class="label">
    <label :for="name">{{ name }}</label>
    <div class="error">{{ error }}</div>
   </div>

   <input type="text" :id="name" v-model="value">
 </div>
</template>

<script>
export default {
  name: 'Input',
  props: {
    name: {
      type: String,
      required: true
    },
    rules: {
      type: Object
    }
  },
  data(){
    return {
      value: ''
    }
  },
  computed:{
    error(){
      if(this.rules.required && !this.value){
        return 'Requerido'
      }
      if(this.rules.min && this.value.length < this.rules.min){
        return `Debe ingresar un mínimo de ${this.rules.min} caracteres`
      }
      return ''
    }
  }
}
</script>

<style scoped>
  .input-wrapper{
    display: flex;
    flex-direction: column;
  }

  .label{
    display: flex;
    justify-content: space-between;
  }

  input {
    background: none;
    color: black;
    border: 1px solid silver;
    border-radius: 5px;
    padding: 10px;
    font-size: 16px;
    margin: 5px 0;
  }

  .error {
    color: red;
  }
</style>
