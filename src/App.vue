<script setup>
import { RouterLink, RouterView } from 'vue-router'
import FooterComponent from './components/FooterComponent.vue';
</script>

<template>
  <header class="nav-container">
    <input type="checkbox" id="menu-toggle" class="menu-toggle">
    <label for="menu-toggle" class="dropdown-btn">&#9776;</label>
    <nav class="links-container">
      <ul>
        <li><RouterLink class="nav-link" to="/">Home</RouterLink></li>
        <li><RouterLink class="nav-link" to="/about">About</RouterLink></li>
        <li><RouterLink class="nav-link" to="/contact">Contact</RouterLink></li>
        <li><RouterLink class="nav-link" to="/skills">Skills</RouterLink></li>
        <li><RouterLink class="nav-link" to="/HobbiesView">Hobbies</RouterLink></li>
        <li><RouterLink class="nav-link" to="/SummaryView">Summary</RouterLink></li>
      </ul>
    </nav>
  </header>

  <div class="page-container">
    <div class="content-wrapper">
      <RouterView />
    </div>
    <footer class="amazing-footer">
      <FooterComponent/>
    </footer>
  </div>
</template>

<style scoped>
/* Updated styles for a visually appealing design */
.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  background-color: #f1f1f1;
  font-family: 'Arial', sans-serif;
}

.content-wrapper {
  flex: 1;
  padding: 20px;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #34495e;
  padding: 10px 20px;
  position: relative;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.2);
  color: #ecf0f1;
}

.links-container ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
}

.links-container ul li {
  margin-right: 20px;
}

.nav-link {
  text-decoration: none;
  color: #ecf0f1;
  font-size: 1.1em;
  transition: background-color 0.3s, color 0.3s;
  border-radius: 4px;
}

.nav-link:hover {
  background-color: #2c3e50;
}

.router-link-active {
  color: #e74c3c;
  background-color: #c0392b;
}

.menu-toggle {
  display: none;
}

.dropdown-btn {
  display: none;
  background-color: #2c3e50;
  color: #ecf0f1;
  padding: 10px 15px;
  border: none;
  cursor: pointer;
  border-radius: 4px;
  font-size: 1.2em;
}

.links-container {
  display: flex;
  align-items: center;
  margin-top: 10px;
}

@media (max-width: 768px) {
  .dropdown-btn {
    display: block;
  }

  .links-container {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background-color: #2c3e50;
  }

  .menu-toggle:checked + .dropdown-btn + .links-container {
    display: flex;
  }
}
</style>
