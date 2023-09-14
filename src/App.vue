<template>
  <div class="content">
    <Introduction />
    <FormFreeTrial />
  </div>
</template>

<script >
import Introduction from "./components/Introduction.vue";
import FormFreeTrial from "./components/FormFreeTrial.vue";

export default {
  components: { Introduction, FormFreeTrial },
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
