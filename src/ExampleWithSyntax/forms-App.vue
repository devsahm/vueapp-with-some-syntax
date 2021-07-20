<template>
<div>
    <pre>
        {{JSON.stringify(formValues, null, 2)}}
    </pre>
</div>
<form @submit.prevent="submitForm">
    <div>
        <label for="name">Name</label>
        <input type="text" id="name" v-model.trim.lazy="formValues.name">
    </div>

    <div>
        <label for="name">Profile Summary</label>
        <textarea type="text" id="profile" v-model="formValues.profile"/>
    </div>

     
    
    <div>
        <label for="country">Country</label>
        <select name="" id="country" v-model="formValues.country">
            <option value="">Select Country</option>
            <option value="Vietam">Vietam</option>
            <option value="Nigeria">Nigeria</option>
            <option value="Singapore">Singore</option>
        </select>
    </div>
<br>
    <div>
        <label for="job-location">Job Location</label>
        <select  id="job-location" multiple v-model="formValues.JobLocation">
            <option value="Vietam">Vietam</option>
            <option value="Nigeria">Nigeria</option>
            <option value="Singapore">Singore</option>
        </select>
    </div>
    <br>

    <div>
         <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no" >
         <label for="remoteWork">Open for Remote Work?</label>
    </div>

    <div>
        <label for="">Skill Set</label>
        <input type="checkbox" id="html" value="HTML" v-model="formValues.skillSet">
        <label for="html">HTML</label>
        <input type="checkbox" id="css" value="CSS" v-model="formValues.skillSet">
        <label for="css">CSS</label>
        <input type="checkbox" id="javascript" value="JAVASCRIPT" v-model="formValues.skillSet">
        <label for="javascript">JAVASCRIPT</label>
    </div>

    <div>
        <label for="remoteWork">Years of Experience</label>
         <input type="radio" id="0-2" v-model="formValues.yearsOfExperience">
         <label for="0-2">0-2</label>
          <input type="radio" value="3-5" id="3-5" v-model="formValues.yearsOfExperience">
         <label for="3-5">3-5</label>
          <input type="radio" value="6-8" id="6-8" v-model="formValues.yearsOfExperience">
         <label for="6-8">6-8</label>
          <input type="radio" value="9-11" id="9-11" v-model="formValues.yearsOfExperience">
         <label for="9-11">9-11</label>
         
    </div>
<div>
        <label for="name">Age</label>
        <input @keyup.enter="submitForm" type="number" id="age" v-model.number="formValues.age"/>
    </div>
    <!-- <div>
        <button>Submit</button>
    </div> -->

</form>
</template>

<script>
export default {
    name: 'App',

    data() {
    return {
        formValues:{
            name: '',
            profile: '',
            country: '',
            JobLocation: [],
            remoteWork: "no",
            skillSet: [],
            yearsOfExperience: '',
            age:null
        }
    }  
    },

    methods: {

        submitForm() {
            console.log('Form Values', this.formValues)
        }
    }


}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}

label{
    font-weight: bold;
    display: flex;
    margin-bottom: 5px;
}

input + label{
    font-weight: bold;
    display: inline-flex;
    margin-right: 20px;
}

input[text]{
padding: 4px;
border: 1px solid gray;
}


</style>
