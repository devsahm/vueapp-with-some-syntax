<template>
<div>{{greet}} {{name}}</div>
<div v-html="hack"></div>
<h2 :id="headingId">Heading</h2>
<h2 class="underline">Underline Text</h2>
<h2 :class="s">Status</h2>
<h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
<h2 :class="isSoldout? 'sold-out':'new'">Soldout</h2>
<h2 :class="['new', 'promoted']">Newly Promoted Movie</h2>
<h2 :class="[isPromoted && 'promoted', isSoldout ? 'sold-out':'new']">Array Conditional Movie</h2>
<h2 :class="{
  promoted:isPromoted,
  new: !isSoldout,
  'sold-out': isSoldout
}"> Object Conditional Movie</h2>
<button :disabled="isDisabled">My App</button>
  <h2 :style="{
    color:hightlightColor,
    fontSize : headerSize + 'px',
    padding : '20px'
  }">Inline Style</h2> 

<h2 :style="headerStyleObject">Inline Style with Object</h2> 

<div :style="[baseStyleObject, successStyleObject]">Success Style</div>

<div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>

</template>
<script>

export default {
  name: 'App',
  data(){
    return {
      greet:"Hello",
      name:"Oluwabamise",
      hack:`<a href='#' onclick='alert("you have been hacked")'>Win a Price</a>`,
      headingId:'heading',
      isDisabled:false,
      status:'danger',
      isPromoted:true,
      isSoldout:true,
      hightlightColor:'orange',
      headerSize:50,
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding : '20px'
      },

      baseStyleObject: {
        fontSize: '50px',
        padding:'10px'
      },

      successStyleObject:{
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green'
      },

      dangerStyleObject:{
        color: 'darkred',
        backgroundColor:'red',
        border:'1px solid red'
      }

    };
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

.underline{
  text-decoration: underline;
}

.promoted{
  font-style: italic;
}
.new{
  color:green;
}

.sold-out{
  color:red;
}
</style>
