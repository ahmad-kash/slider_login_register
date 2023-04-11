<template>
  <form @submit.prevent="login">
    <div class="flex flex-col p-8">
      <h1 class="text-2xl text-center text-gray-800 mb-12 font-bold">
        Sign in
      </h1>
      <div class="flex flex-col space-y-5">
        <Input
          id="email"
          name="email"
          type="email"
          required
          autocomplete="email"
          placeholder="Email"
          v-model="data.email"
        />
        <Input
          id="password"
          name="password"
          type="password"
          required
          autocomplete="password"
          placeholder="password"
          v-model="data.password"
        />
        <a href="#" class="text-blue-800">Forgot your password?</a>
      </div>
      <Button class="mt-12">login</Button>
    </div>
  </form>
</template>
<script setup>
import Input from "./Input.vue";
import Button from "./Button.vue";
import { reactive } from "vue";
const data = reactive({
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
