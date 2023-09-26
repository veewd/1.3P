<template>
    <div>
      <!-- Header -->
      <header>
        <h1>Hobbies</h1>
        <link rel="icon" href="/favicon.ico" /> <!-- Favicon -->
      </header>
  
      <!-- Content -->
      <main>
        <!-- Text (h3) -->
        <h3>My Hobbies</h3>
        <p>Here are some of my favourite hobbies:</p>
  
        <!-- Using v-for to loop through hobbies -->
        <ul>
          <li v-for="(hobby, index) in hobbies" :key="index">
            {{ hobby.name }}
            <p>{{ hobby.description }}</p>
  
            <!-- Using v-if to conditionally display extra information -->
            <div v-if="hobby.name === 'Technology'">
              <input type="text" v-model="technologyInterest" placeholder="Your technology interests">
            </div>
  
            <div v-if="hobby.name === 'Reading'">
              <input type="text" v-model="favoriteBook" placeholder="Your favorite book">
            </div>
  
            <!-- Using v-model to bind input values to data properties -->
            <div v-if="hobby.name === 'Sports'">
              <input type="text" v-model="favoriteSport" placeholder="Your favorite sport">
            </div>
          </li>
        </ul>
      </main>
    </div>
  </template>
  
  <script setup>

  import './Hobbies.css'
  import { ref } from 'vue';
  
  // Data properties for user inputs
  const technologyInterest = ref('');
  const favoriteBook = ref('');
  const favoriteSport = ref('');
  
  // Array of hobbies
  const hobbies = ref([
    {
      name: 'Technology',
      description: 'I like learning about new developments in the science & tech field. The topics I am keen about are Artificial intelligence & Quantum computing',
    },
    {
      name: 'Reading',
      description: 'I like reading and was an avid book reader when I was a kid. I like adventure/mystery genre in fiction and history, geography subject related content in non-fiction. I also like reading and catching up with current affairs.',
    },
    {
      name: 'Sports',
      description: 'I like watching sports, especially cricket and football. I loved playing these two sports as a kid and was very active in school. I am a big fan of Liverpool FC.',
    },
  ]);
  </script>
  
  
  
  