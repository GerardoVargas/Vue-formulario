/* 
  EN UN SFC (Single File Component) se trabaja en 3 secciones:
  - Template
  - Script
  - Styles
 */

<template>
   <div>
     <h2>Componente de prueba</h2>
   </div>
</template>

<script>

export default {
  name: 'Prueba'
}
</script>
 
 <style scoped>
  div{
    color: red;
  }
 </style>