<script setup>
import { ref } from "vue";
import axios from "axios";
import { useRouter } from "vue-router";

const router = useRouter();
const form = ref({
  name: "",
  email: "",
  password: "",
  password_confirmation: "",
});

const handleRegister = async () => {
  await axios.post("/register", {
    name: form.value.name,
    email: form.value.email,
    password: form.value.password,
    password_confirmation: form.value.password_confirmation
  });
  router.push("/");
};
</script>

<template>
  <div class="h-screen flex">
    <div
      class="flex w-full lg:w-1/2 justify-center items-center bg-white space-y-8 mx-auto"
    >
      <div class="w-full px-8 md:px-32 lg:px-24">
        <form class="bg-white rounded-md shadow-2xl p-5" @submit="handleRegister">
          <h1 class="text-gray-800 font-bold text-2xl mb-1">
            Create a new account
          </h1>
          <p class="text-sm font-normal text-gray-600 mb-8"></p>
          <div class="flex items-center border-2 mb-8 py-2 px-3 rounded-2xl">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              width="24px"
              height="24px"
              viewBox="0 0 24 24"
              version="1.1"
              class="text-gray-400"
              fill="none"
            >
              <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
                <polygon points="0 0 24 0 24 24 0 24" />
                <path
                  d="M12,11 C9.790861,11 8,9.209139 8,7 C8,4.790861 9.790861,3 12,3 C14.209139,3 16,4.790861 16,7 C16,9.209139 14.209139,11 12,11 Z"
                  fill="#9ca3af"
                  fill-rule="nonzero"
                  opacity="0.3"
                />
                <path
                  d="M3.00065168,20.1992055 C3.38825852,15.4265159 7.26191235,13 11.9833413,13 C16.7712164,13 20.7048837,15.2931929 20.9979143,20.2 C21.0095879,20.3954741 20.9979143,21 20.2466999,21 C16.541124,21 11.0347247,21 3.72750223,21 C3.47671215,21 2.97953825,20.45918 3.00065168,20.1992055 Z"
                  fill="#9ca3af"
                  fill-rule="nonzero"
                />
              </g>
            </svg>
            <input
              id="name"
              class="pl-2 w-full outline-none border-none"
              type="text"
              name="name"
              placeholder="Full name"
              v-model="form.name"
            />
          </div>
          <div class="flex items-center border-2 mb-8 py-2 px-3 rounded-2xl">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 text-gray-400"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                strokeLinecap="round"
                strokeLinejoin="round"
                strokeWidth="2"
                d="M16 12a4 4 0 10-8 0 4 4 0 008 0zm0 0v1.5a2.5 2.5 0 005 0V12a9 9 0 10-9 9m4.5-1.206a8.959 8.959 0 01-4.5 1.207"
              />
            </svg>
            <input
              id="email"
              class="pl-2 w-full outline-none border-none"
              type="email"
              name="email"
              placeholder="Email Address"
              v-model="form.email"
            />
          </div>
          <div class="flex items-center border-2 mb-12 py-2 px-3 rounded-2xl">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 text-gray-400"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                fillRule="evenodd"
                d="M5 9V7a5 5 0 0110 0v2a2 2 0 012 2v5a2 2 0 01-2 2H5a2 2 0 01-2-2v-5a2 2 0 012-2zm8-2v2H7V7a3 3 0 016 0z"
                clipRule="evenodd"
              />
            </svg>
            <input
              class="pl-2 w-full outline-none border-none"
              type="password"
              name="password"
              id="password"
              placeholder="Password"
              v-model="form.password"
            />
          </div>
          <div class="flex items-center border-2 mb-12 py-2 px-3 rounded-2xl">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 text-gray-400"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                fillRule="evenodd"
                d="M5 9V7a5 5 0 0110 0v2a2 2 0 012 2v5a2 2 0 01-2 2H5a2 2 0 01-2-2v-5a2 2 0 012-2zm8-2v2H7V7a3 3 0 016 0z"
                clipRule="evenodd"
              />
            </svg>
            <input
              class="pl-2 w-full outline-none border-none"
              type="password"
              name="password_confirmation"
              id="password_confirmation"
              placeholder="Confirm password"
              v-model="form.password_confirmation"
            />
          </div>
          <button
            type="submit"
            class="block w-full bg-indigo-600 mt-5 py-2 rounded-2xl hover:bg-indigo-700 hover:-translate-y-1 transition-all duration-500 text-white font-semibold mb-2"
          >
            Register
          </button>
          <div class="flex justify-center mt-4">
            <router-link
              :to="{ name: 'Login' }"
              href="#"
              class="text-sm ml-2 hover:text-blue-500 cursor-pointer hover:-translate-y-1 duration-500 transition-all"
              >Already registered ?</router-link
            >
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.login_img_section {
  background: linear-gradient(rgba(2, 2, 2, 0.7), rgba(0, 0, 0, 0.7)),
    url(https://images.unsplash.com/photo-1650825556125-060e52d40bd0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80)
      center center;
}
</style>
