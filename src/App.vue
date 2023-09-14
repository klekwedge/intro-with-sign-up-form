<template>
  <div class="content">
    <Input />
    <SubmitButton/>
  </div>
</template>

<script >
import Input from "./components/Input.vue";
import SubmitButton from "./components/SubmitButton.vue";


export default {
  components: { Input, SubmitButton },
  setup() {
    return {};
  },
};
</script>

<style scoped>
.content {
  display: flex;
  align-items: center;
  margin: 0 auto;
  max-width: 1400px;
  padding-top: 200px;
}

.content > div {
  flex: 0 1 50%;
}

@media (max-width: 1200px) {
  .content {
    padding-top: 80px;
    gap: 3rem;
    flex-direction: column;
  }
}
</style>
