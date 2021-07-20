<template>
<h2 v-for="name in names" :key="name"> {{name}}</h2>
<h2 v-for="name in fullNames" :key="name.last">{{name.first}} {{name.last}}</h2>
<h2 v-for="(name, index) in names" :key="name"> {{index}} {{name}}</h2>

<div v-for="actor in actors" :key="actor.name">
<h2>{{actor.name}}</h2>
<h3 v-for="movie in actor.movies" :key="movie">{{movie}}</h3>
</div>

<h2 v-for="(value, key, index) in myInfo" :key="value">{{index}} {{key}} {{value}}</h2>

<template v-for="name in names" :key="name">
  <h2>{{name}}</h2
  ><hr>
  </template>

</template>

<script>
export default {
    name: 'App',

    data() {
    return {
       names:['Bruces', 'Clork', 'Diana'],
       fullNames: [   
           {first:'Bruce', last:'Damake'},
           {first:'Clark', last:'Johnson'},
           {first:'princess', last:'Diana'}
       ],

       actors: [
         {
           name:'Christain Bale',
           movies: ['Batman', 'Prestige']
         },
         
         {
           name: 'Di Caprio',
           movies: ['Titanic', 'Incepion']
         }
       ],

       myInfo:{
         name: 'Samuel',
         channel: 'Code Evolution',
         course: 'Vue 3'
       }

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
