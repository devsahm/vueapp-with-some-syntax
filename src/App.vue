<template>
<h2>Volume Tracker (0-2)</h2>
<h3>Current Volume  {{volume}}</h3>

<div>

    <button @click="volume +=2"> Increase</button>
    <button @click="volume -=2"> Decrease</button> 
    <button @click="movieList.push('Wonder Woman')">Add Movie</button> 
    <!-- Pushing an item into an array and watching it the watcher -->
    <br> <br> 
    <input type="text" v-model="movie">
    <input type="text" v-model="movieInfo.title">
    <input type="text" v-model="movieInfo.actor">
</div>
</template>

<script>
export default {
 name: 'App',

    data() {
        return {
         volume: 0,
         movie: 'Batman',
         movieInfo: {
             title: '',
             actor: ''
         },
         movieList: ['Batman', 'Spiderman'],
        }
    },

    methods: {
    },

    computed: {
    },

    watch :{
        volume(newVolume, oldVolume){
            if(newVolume > oldVolume && newVolume === 16){
                alert('Listening to high volume can damage your air drum')
            }
        },

        movie: {
            handler(newValue){
            console.log(`calling API with the new name= ${newValue}`)
              },
            immediate: true
        },

        movieInfo: {
            handler(newValue){
                console.log(
                    `Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`
                )
            },
            deep:true
        },

        movieList: {
            handler(newValue){
                console.log(`Updated Lists is ${newValue}`)
            },
            deep:true
        }
    }
  
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
