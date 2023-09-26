<template>
    <div class="Contact-me-form">
      <h2>Contact Me Form</h2>
      <form @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="name/company">Your name/company:</label>
          <input type="text" id="Your name/company" v-model="formData.name" required />
        </div>
  
        <div class="form-group">
          <label for="email">Your Email:</label>
          <input type="email" id="Your email" v-model="formData.email" required />
        </div>
  
        <div class="form-group">
          <label for="feedback">Your Feedback:</label>
          <textarea id="Your feedback" v-model="formData.feedback" required></textarea>
        </div>
  
        <button type="submit">Submit</button>
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const formData = ref({
    name: '',
    email: '',
    feedback: ''
  });
  
  const handleSubmit = () => {
    // Handle the form submission logic here
    // For demonstration purposes, we'll just log the form data
    console.log(formData.value);
  
    // Reset the form
    formData.value = {
      name: '',
      email: '',
      feedback: ''
    };
  };
  </script>
  
  <style scoped>
  .about-us-form {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    margin-bottom: 10px;
  }
  
  input[type="text"],
  input[type="email"],
  textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  button {
    padding: 10px 15px;
    background-color: #007BFF;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  