<script lang="ts" setup>
import { computed } from "vue";
import store from "../store";

const meals = computed(() => store.state.meals);

const letters = "ABCÇDEFGĞHIİJKLMNOÖQPRSŞTUÜVXYZ".split("");
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
</template>
