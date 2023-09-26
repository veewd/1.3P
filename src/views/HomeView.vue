<template>
  <section class="portfolio-home">
    <header class="portfolio-header">
      <h1>Rishubh Sethi</h1>
      <p>Web Developer & Designer</p>
    </header>

    <section class="portfolio-intro">
      <p>
        Hello, I am Rish, a web developer with several years of experience. I like making responsive and intuitive websites about various subjects!
      </p>
    </section>

    <section class="portfolio-projects">
      <h2>Study Background</h2>
      <div class="projects-grid">
        <!-- Loop for the first set of projects -->
        <div v-for="project in projects" :key="project.id">
          <h3>{{ project.name }}</h3>
          <p>{{ project.description }}</p>
          <img class="project-image" :src="project.image1" :alt="project.name" width="350" height="350" />
        </div>

        <!-- Loop for the second set of projects -->
        <div  v-for="project in projects_2" :key="project.id">
          <h3>{{ project.name }}</h3>
          <p>{{ project.description }}</p>
          <img class="project-image" :src="project.image2" :alt="project.name" width="350" height="350" />
        </div>
      </div>
    </section>

    <footer class="portfolio-footer">
      <p>Thank you for visiting! Let's <a href="mailto:john@example.com">connect</a>.</p>
    </footer>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const projects = ref([
  {
    id: 1,
    name: 'Programming Knowledge',
    description: 'I have successfully learned key programming languages like C++, Python, and C#',
    image1: '/learn-programming-career-jpg.webp', // Replace with your image URL
  }
]);

const projects_2 = ref([
  {
    id: 2,
    name: 'HTML & CSS',
    description: 'I have learned and worked on HTML & CSS projects in web development',
    image2: '/software-dev.jpg', // Replace with your image URL
  },
  // Add more projects as needed
]);
</script>\

<style scoped>
/* Your existing styles */

.projects-grid {
  display: flex;
  flex-wrap: wrap; /* Allow projects to wrap to the next row if there's not enough horizontal space */
  justify-content: space-between; /* Distribute projects evenly across the available horizontal space */
  gap: 20px; /* Add some spacing between projects */
}

.project-card {
  flex-basis: calc(50% - 10px); /* Set the width of each project to 50% with 10px spacing in between */
  text-align: center; /* Center project content horizontally */
  padding: 10px; /* Add some padding around each project */
  border: 1px solid #ccc; /* Add a border for better separation (optional) */
}

.project-card img.project-image {
  max-width: 100%; /* Ensure the image doesn't exceed the width of the project card */
  height: auto; /* Automatically adjust the height to maintain aspect ratio */
  display: block; /* Display images as block elements */
  margin: 0 auto; /* Center the image horizontally within the project card */
}
</style>
