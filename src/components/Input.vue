<template>
  <div class="input-block">
    <input
      :type="type"
      :class="{ error: error }"
      :placeholder="placeholder"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
    />
    <span v-if="error" class="error-msg"
      >The {{ placeholder }} cannot be empty
    </span>
    <img
      v-if="error"
      class="icon-error"
      src="/images/icon-error.svg"
      alt="error icon"
    />
  </div>
</template>
<script setup>
const { type, placeholder, modelValue, error } = defineProps([
  "type",
  "placeholder",
  "modelValue",
  "error",
]);
</script>

<style scoped>
input {
  padding: 15px;
  border-radius: 5px;
  border: 2px solid var(--graylishBlue);
  font-size: 16px;
  padding-left: 25px;
  font-weight: 500;
  position: relative;
  margin-bottom: 10px;
}

.input-block {
  position: relative;
  display: flex;
  flex-direction: column;
}

input:focus {
  outline: none !important;
  border: 2px solid var(--blue);
}

.error {
  border: 2px solid var(--red);
}

.error-msg {
  font-style: italic;
  font-size: 12px;
  text-align: right;
  color: var(--red);
  font-weight: 600;
  position: absolute;
  bottom: -10px;
  right: 0;
}

.icon-error {
  position: absolute;
  right: 15px;
  top: 18px;
}
</style>