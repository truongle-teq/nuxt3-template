<script setup lang="ts">
import Button from "~/components/Button.vue";

// const handleClick = () => {
//   console.log("clicked");
// };

const handleEmitted = (value: string) => {
  console.log(value);
};
</script>
<template>
  <div>
    <h1>Page</h1>
    <Button text="This is a Button" @on-click-emit="handleEmitted" />
  </div>
</template>
