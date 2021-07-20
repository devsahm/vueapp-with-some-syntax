<template>
<template v-for="name in names" :key="name">
    <h2 v-if="name==='Bruces'">{{name}}</h2></template>
<!-- I tried this myself -->
<!-- <template v-for="school in schools" :key="school.name">
    <h3 v-if="school.class=='SS2'">{{school.name}} {{school.class}}</h3>
</template> -->
</template>

<script>
export default {
    name: 'App',

    data() {
    return {
       names:['Bruces', 'Clork', 'Diana'],
       schools: [
           { name:'Omolabake', class: 'Jss1'},
           {name: 'Ecowas', class: 'SS2'},
           {name: 'Genius', class: 'SS2'}
       ]
    } 
         
    },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
