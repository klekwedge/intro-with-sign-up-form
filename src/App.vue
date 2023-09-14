<template>
  <div class="content">
    <Input />
    <SubmitButton />
    <Introduction />
    <FreeTrial />
  </div>
</template>

<script >
import Input from "./components/Input.vue";
import SubmitButton from "./components/SubmitButton.vue";
import Introduction from "./components/Introduction.vue";
import FreeTrial from "./components/FreeTrial.vue";

export default {
  components: { Input, SubmitButton, Introduction, FreeTrial },
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
