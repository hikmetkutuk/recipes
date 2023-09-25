<template>
    <v-app-bar app>
      <router-link :to="{ name: 'home' }" class="my-title">
        <v-toolbar-title>recipes</v-toolbar-title>
      </router-link>
      <v-spacer></v-spacer>
      <div class="my-links">
        <router-link to="/" class="my-link">
          Search Meals
        </router-link>
        <router-link to="/" class="my-link">
          Meals By Letter
        </router-link>
      </div>
    </v-app-bar>
  </template>
  
  <style scoped>
  .my-title {
    text-decoration: none;
    color: #ff9900;
    padding: 1rem;
  }
  
  .my-links {
    display: flex;
    align-items: center;
  }
  
  .my-link {
    color: #000;
    text-decoration: none;
    font-size: 18px;
    padding: 1rem;
  }
  
  .my-link:hover {
    color: #ff9900;
  }
  </style>
  