<template>
 <div class='input-wrapper'>
   <div class="label">
    <label :for="name">{{ name }}</label>
    <div class="error">{{ error }}</div>
   </div>

   <input type="text" :id="name" :value="value" @input='input'>
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
    },
    value:{
      type: String
    }
  },
  computed:{
    error(){
      return this.validar(this.value)
    }
  },
  methods:{
    input($evt){
      this.$emit('update', {
        value: $evt.target.value,
        name: this.name,
        valid: this.validar($evt.target.value) ? false : true
      });
    },
    validar(value){
      if(this.rules.required && !value){
        return 'Requerido'
      }
      if(this.rules.min && value.length < this.rules.min){
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
