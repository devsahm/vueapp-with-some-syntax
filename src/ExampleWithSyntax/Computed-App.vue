<template>
    

    <button @click="name='John'">Change Name</button>

    <button @click="changeFullName">Change FullName</button>

<button @click="items.push({id:4, title:'Dove', price:980})">Push to array</button>
    <h1>{{firstname}} {{lastname}}</h1>
    <h1>Computed- {{fullName}}</h1>
    <h1>Total - {{total}}</h1>

    <!-- <template v-for="item in items" :key="item.id">
        <h2 v-if="item.price > 100">{{item.title}} {{item.price}}</h2>
    </template> -->

    <h2 v-for="item in expensiveItem" :key="item.id"> {{item.title}} {{item.price}}</h2>
</template>

<script>

export default {
 name: 'App',

    data() {
        return {
          firstname: "Samuel",
          lastname: "Damilare",
          items : [
              {
                  id: 1,
                  title: "TV",
                  price:2000
              },
              {
                  id:2,
                  title:"Phone",
                  price:3000
              },
              {
                  id:3,
                  title: "Laptop",
                  price:100
              }
          ] 
        }
    },

    methods : {
        changeFullName(){
            this.fullName = "John Snow"
        }
    },

    computed: {
        fullName: {
            get(){
                return `${this.firstname} ${this.lastname}`
            },

            set(value){
                const names = value.split(' ')
                this.firstname = names[0]
                this.lastname = names[1]
            }
        },

        total(){
            return this.items.reduce((total, curr) => (total= total + curr.price), 0)
        },

        expensiveItem(){
            return this.items.filter(item => item.price > 100)
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
