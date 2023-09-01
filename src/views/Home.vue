<script lang="ts" setup>
import { computed, onMounted, ref } from "vue";
import store from "../store";
import axiosClient from "../axiosClient";

const meals = computed(() => store.state.meals);

const letters = "ABCÇDEFGĞHIİJKLMNOÖQPRSŞTUÜVXYZ".split("");
const ingredients = ref([])

onMounted(async () => {
  const response = await axiosClient.get("/list.php?i=list");
  ingredients.value = response.data;
});
</script>

<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="8">
        <v-text-field
          clearable
          rounded
          variant="outlined"
          label="Search for Meals"
        ></v-text-field>
      </v-col>
    </v-row>
    <v-row justify="center">
      <v-col cols="auto" v-for="letter of letters" :key="letter">
        <router-link :to="{ name: 'byLetter', params: { letter } }">
          {{ letter }}
        </router-link>
      </v-col>
    </v-row>
  </v-container>

  <pre>{{ ingredients }}</pre>
</template>
