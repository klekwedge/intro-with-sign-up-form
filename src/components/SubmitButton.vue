<template>
  <button class="small-shadow">{{ text }}</button>
</template>

<script setup>
const { text } = defineProps(["text"]);
</script>
<style scoped>
button {
  color: var(--white);
  background-color: var(--green);
  border: none;
  padding: 15px 0;
  border-radius: 10px;
  text-transform: uppercase;
  font-size: 18px;
  font-weight: 500;
}

button:hover {
  cursor: pointer;
  background-color: var(--greenPointer);
}
</style>