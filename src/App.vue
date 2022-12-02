<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
import { useCounterStore } from "@/stores/counter";
const counter = useCounterStore();
const add = () => {
  counter.count++;
  console.log(counter.count);
};
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
      <button @click="add">Add</button>
    </div>
  </header>

  <RouterView />

  <pre>{{ counter }}</pre>
</template>

<style scoped></style>
