<template>
    <div>
      <h1 class="heading">My Skills</h1>
  
      <!-- HTML Elements: Table -->
      <h2 class="sub-heading">Technical Knowledge</h2>
      <table class="skills-table">
        <thead>
          <tr>
            <th>Programming</th>
            <th>Web development</th>
            <th>Design</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>C#</td>
            <td>HTML</td>
            <td>Wordpress trained</td>
          </tr>
          <tr>
            <td>Python</td>
            <td>CSS</td>
            <td>Dreamweaver</td>
          </tr>
        </tbody>
      </table>
  
      <!-- User Input: Approve or Reject -->
      <h2 class="sub-heading">Approve or Reject Skills</h2>
      <form @submit.prevent="handleApproval">
        <label for="approval">Do you approve my skills?</label>
        <div>
          <input type="radio" id="yes" name="approval" value="yes" v-model="approval"> Yes
          <input type="radio" id="no" name="approval" value="no" v-model="approval"> No
        </div>
       
      </form>
  
      <!-- Output Message -->
      <div v-if="approval !== ''" class="output-message">
        <p v-if="approval === 'yes'">Congratulations! Your skills are approved.</p>
        <p v-else-if="approval === 'no'">Unfortunately, your skills are not approved.</p>
      </div>
      <button type="submit">Submit</button>
    </div>
  </template>
  
  <script>
  // Your JavaScript logic can go here if needed
  export default {
    data() {
      return {
        approval: '', // Initial value for user approval
      };
    },
    methods: {
      handleApproval() {
        // Logic to handle user approval/rejection can go here
        // You can use this.approval to access the user's choice
      },
    },
  };
  </script>
  
  <style>
  .heading {
    background-color: red;
    color: yellow;
  }
  
  .sub-heading {
    margin-top: 20px; /* Add spacing below the main heading */
  }
  
  /* Add border styles to table */
  .skills-table {
    border-collapse: collapse; /* Collapse table borders into a single border */
    width: 100%;
  }
  
  .skills-table th,
  .skills-table td {
    border: 1px solid #ccc; /* Add a 1px solid border to table headers and cells */
    padding: 8px; /* Add padding for better spacing */
    text-align: center; /* Center-align text in table cells */
  }
  
  /* Add styles for user input form */
  form {
    margin-top: 20px;
  }
  
  /* Add styles for output message */
  .output-message {
    margin-top: 20px;
    font-weight: bold;
  }
  </style>
  