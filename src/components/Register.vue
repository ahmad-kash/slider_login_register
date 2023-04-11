<template>
  <form @submit.prevent="login">
    <div class="flex flex-col p-8">
      <h1 class="text-2xl text-center text-gray-800 mb-12 font-bold">
        Register
      </h1>
      <div class="flex flex-col space-y-5">
        <Input
          id="name"
          name="name"
          type="name"
          required
          autocomplete="name"
          placeholder="Name"
          v-model="data.name"
        />
        <Input
          id="-reg-email"
          name="email"
          type="email"
          required
          autocomplete="email"
          placeholder="Email"
          v-model="data.email"
        />
        <Input
          id="reg-password"
          name="password"
          type="password"
          required
          autocomplete="password"
          placeholder="password"
          v-model="data.password"
        />
      </div>
      <Button class="mt-12">register</Button>
    </div>
  </form>
</template>
<script setup>
import Input from "./Input.vue";
import Button from "./Button.vue";
import { reactive } from "vue";
const data = reactive({
  name: "",
  email: "",
  password: "",
});
function login() {
  // put your login logic here
  console.log(
    `name: ${data.name}, email: ${data.email}, password: ${data.password}`
  );
}
</script>
