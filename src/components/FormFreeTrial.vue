<template>
  <div class="form-block">
    <FreeTrial />
    <div class="form shadow">
      <form @submit.prevent="onSubmitForm">
        <Input
          type="text"
          placeholder="First Name"
          v-model="formData.firstName.value"
          :error="formData.firstName.error"
        />
        <Input
          type="text"
          placeholder="Last Name"
          v-model="formData.lastName.value"
          :error="formData.lastName.error"
        />
        <Input
          type="email"
          placeholder="Email Address"
          v-model="formData.email.value"
          :error="formData.email.error"
        />
        <Input
          type="password"
          placeholder="Password"
          v-model="formData.password.value"
          :error="formData.password.error"
        />
        <SubmitButton text="Claim your free trial" />
      </form>
      <p class="terms-content">
        By clicking the button, you are agreeing to our
        <span class="terms">Terms and Services</span>
      </p>
    </div>
  </div>
</template>
<script setup>
import { reactive } from "vue";

import FreeTrial from "./FreeTrial.vue";
import SubmitButton from "./SubmitButton.vue";
import Input from "./Input.vue";

const formData = reactive({
  firstName: { value: "", error: false },
  lastName: { value: "", error: false },
  email: { value: "", error: false },
  password: { value: "", error: false },
});

const onSubmitForm = () => {
  let errorCounter = 0;
  const formFormat = Object.entries(formData);

  formFormat.forEach((el) => {
    const value = el[1].value;
    if (value == "") {
      el[1].error = true;
      errorCounter++;
    } else {
      el[1].error = false;
    }
  });

  if (errorCounter > 0) {
    console.log("The form is not submitted");
  }
};
</script>

<style scoped>
.form-block {
  max-width: 560px;
}
.form {
  margin-top: 30px;
  background-color: var(--white);
  padding: 30px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.terms-content {
  font-size: 12px;
  text-align: center;
  color: var(--graylishBlue);
  font-weight: 500;
}

.terms {
  color: var(--red);
  cursor: pointer;
}
</style>