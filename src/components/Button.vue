/* 
  EN UN SFC (Single File Component) se trabaja en 3 secciones:
  - Template
  - Script
  - Styles
 */

<template>
  <button 
    :style="{ background, color }"
  >
    Prueba
  </button>
</template>

<script>

export default {
  name: 'Button',
  props:{
    color: {
      type: String
    },
    background: {
      type: String
    },
    isDisabled: {
      type: Boolean
    }
  }
}
</script>
 
 <style scoped>
  button {
    background: none;
    color: black;
    border: none;
    border-radius: 5px;
    padding: 10px 40px;
    font-size: 16px;
    cursor: pointer;
  }

  button:hover {
    filter: brightness(125%);
  }
 </style>