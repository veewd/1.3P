<template>
    <div class="content">
      <div class="heading">
        <h1><b><u>Me In Overview</u></b></h1>
      </div>
      <p>
        I am a meticulous and motivated person who likes solving problems since young. That is why I chose a career in IT.
        I am willing to work with companies and individuals across a spectrum of domains to help create unique websites
        catering to specific and unique requirements. I will put in the work and effort to meet client requirements and
        I have the technical know-how to do so. With me, you are guaranteed to have a professional service in web development
        to address your required web-centric needs.
      </p>
  
      <!-- Add an input field with v-model -->
      <div>
        <input type="text" v-model="exampleText" placeholder="Type something...">
        <p>You typed: {{ exampleText }}</p>
      </div>
  
      <button @click="MYComp = 'HomeView'">Home</button> <br>
      <button @click="MYComp = 'HobbiesView'">Hobbies</button><br>
      <button @click="MYComp = 'SkillsView'">Skills</button><br>
      <button @click="MYComp = 'AboutView'">About Me</button><br>
      <button @click="MYComp = 'ContactUs'">Contact</button><br>
      <component :is="MYComp"></component>
    </div>
  </template>
  
  <script>
  import HomeView from '../views/HomeView.vue';
  import HobbiesView from '../views/HobbiesView.vue';
  import SkillsView from '../views/SkillsView.vue';
  import ContactUs from '../views/ContactUs.vue';
  import AboutView from '../views/AboutView.vue';
  
  export default {
    data() {
      return {
        MYComp: '',
        exampleText: '', // Add a data property for v-model
      };
    },
    components: {
      HomeView,
      AboutView,
      HobbiesView,
      SkillsView,
      ContactUs,
    },
  };
  </script>
  
  <style>
  .heading {
    color: darkslateblue;
  }
  
  .content {
    background-color: yellowgreen;
    color: darkviolet;
    width: fit-content;
    padding: 10px;
  }
  </style>
  