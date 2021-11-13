<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <br/>
    <span>  {{ message1 }}  </span><br/>
    <span v-text="message2"></span>
    <hr/>
    <span> {{ counter }} </span> <br/>
    <button v-on:click="counter=counter+1" >+</button>
    <button v-on:click="minus" >-</button>
    <hr/>
    <span>  {{ message3 }}  </span><br/>
    <input type="text" v-model="message3"/>
    <select v-model="message3">
      <option value="choice01">Hello 1 </option>
      <option value="choice02">Hello 2 </option>
      <option value="choice03">Hello 3 </option>
    </select><br/><br/>
    <textarea v-model="message3"></textarea>
    <hr/>
    <input v-bind:type="inputtype" />Correct<br/>
    
    <img v-bind:src="require('@/assets/images/'+imagename)">
    <select v-model="imagename">
      <option value="1.jpg">Image 1 </option>
      <option value="2.jpg">Image 2 </option>
  </select><br/><br/><br/>
  <hr/>

  <h1 v-show="isGreeting"> Hello !!! </h1>
  
  <hr/>
  {{htmlText}}<br/>
  <span v-html="htmlText"></span>
  <hr/>

  <div v-bind:key="emp.id" v-for="emp in employees">
    <b>Id</b>: {{emp.id}},<br/>
    <b>Name</b>: {{emp.name}},<br/>
    <b>Salary</b>: {{emp.Salary}},<br/><br/><br/>
    <b>Name</b>:<span v-bind:class="(emp.Salary>90000) ? 'high' : (emp.Salary>=30000) ? 'medium' : 'low' ">{{emp.name}}</span>,<br/> 
     <b>Salary</b>:{{emp.Salary}},
     <span  v-if="emp.Salary>90000">***</span>
     <span  v-else-if="emp.Salary>=30000">**</span>
     <span  v-else>*</span>


     <br/><br/><br/> 

  </div>
  <hr/>
<div v-bind:key="std.studentId" v-for="std in students"> 
    <b>studentId :</b> {{std.studentId}},<br/>
    <b>firstname :</b> {{std.firstname}},<br/>
    <b>lastname :</b> {{std.lastname}},<br/>
    <b>sscore :</b> {{std.score}},<br/><br/><br/>
  </div>


    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'


export default {
  name: 'App',
  components: {
    //HelloWorld
  },
  data(){
    return {
      message1: "Hello World !!",
      message2: "Hello World Again !!",
      message3: "Type Here!",
      inputtype: "radio",
      imagename:"2.jpg",
      htmlText: "<b>HTML TEXT</b>&nbsp:",
      counter: 0,
      isGreeting: true,
      students: [{"studentId":624235052,"firstname": "Wanasree","lastname":"Sahasantiwarakul","score":"100"},
      {"studentId":624235048,"firstname": "Warinthon","lastname":"Kongjan","score":"100"},
      {"studentId":624235054,"firstname": "Phongpol","lastname":"Nithiverod","score":"100"},
      {"studentId":624235053,"firstname": "Sofwan","lastname":"Jehmuso","score":"100"}]
    }
  },
  methods: {
    minus: function() {
      this.counter=this.counter-2
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
.high{
  color:rgba(69, 69, 158, 0.411);
}
.medium{
  color:rgba(17, 17, 124, 0.541);
}
.low{
  color: rgba(36, 87, 207, 0.691);
}
</style>
