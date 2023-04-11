<template>
  <div
    class="flex flex-col justify-center items-center min-h-screen bg-gray-200"
  >
    <div
      class="flex flex-col md:flex-row border border-gray-300 rounded-lg bg-white shadow-md relative overflow-hidden"
    >
      <Login
        class="md:scale-100 opacity-100 md:relative origin-left duration-1000 transition-all"
        :class="{ 'scale-x-0': !showSignInSm, 'md:opacity-0': !showSignInMd }"
      ></Login>
      <Register
        class="md:scale-100 opacity-100 absolute md:relative origin-right duration-1000 transition-all"
        :class="{ 'scale-x-0': showSignInSm, 'md:opacity-0': showSignInMd }"
      ></Register>
      <div
        class="hidden md:flex justify-center items-center absolute w-1/2 h-full right-0 top-0 z-10 duration-1000 bg-gradient-to-r to-sky-500 from-indigo-500"
        :class="{
          '-translate-x-full bg-gradient-to-r md:from-sky-500 md:to-indigo-500':
            !showSignInMd,
        }"
      >
        <div class="p-8 md:flex flex-col justify-center items-center space-y-5">
          <h1 class="text-white font-bold text-2xl text-center">
            {{ showSignInMd ? "Welcome Back!" : "Welcome" }}
          </h1>
          <p class="text-white text-center">
            {{
              showSignInMd
                ? "To keep connected with us please login with your personal info"
                : "Enter your personal details and start your journey with us"
            }}
          </p>
          <button
            class="px-4 py-2 border text-white active:scale-95 rounded-xl capitalize"
            @click="showSignInMd = !showSignInMd"
          >
            {{
              showSignInMd ? "Register instead?" : "already have an account?"
            }}
          </button>
        </div>
      </div>
      <button
        class="p-2 text-start text-l font-light capitalize w-fit md:hidden text-blue-800"
        @click="showSignInSm = !showSignInSm"
      >
        {{ showSignInSm ? "Register instead?" : "already have an account?" }}
      </button>
    </div>
  </div>
</template>
<script setup>
import Login from "../components/Login.vue";
import Register from "../components/Register.vue";
import { ref, computed } from "vue";
const showSignInSm = ref(true);
const showSignInMd = ref(true);
</script>
