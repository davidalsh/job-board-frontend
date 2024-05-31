<template>
  <div class="py-10 px-6">
    <div class="max-w-sm mx-auto py-10 px-6 bg-gray-100 rounded-xl">
      <h1 class="mb-6 text-2xl">Log in</h1>
      <form @submit.prevent="submitorm">
        <input
          v-model="email"
          type="email"
          placeholder="Email"
          class="w-full mb-4 py-4 px-6 rounded-xl"
        />
        <input
          v-model="password1"
          type="password"
          placeholder="Password"
          class="w-full mb-4 py-4 px-6 rounded-xl"
        />
        <input
          v-model="password2"
          type="password"
          placeholder="Repeat password"
          class="w-full mb-4 py-4 px-6 rounded-xl"
        />

        <div
          class="mb-6 py-4 px-6 bg-rose-400 text-white rounded-xl"
          v-if="errors.length"
        >
          <p v-for="error in errors" :key="error">
            {{ error }}
          </p>
        </div>

        <button class="py-4 px-6 bg-teal-700 text-white rounded-xl">
          Submit
        </button>
      </form>
    </div>
  </div>
</template>

<script setup>
const email = ref("");
const password1 = ref("");
const password2 = ref("");
const errors = ref([]);

async function submitForm() {
  errors.value = [];
  await $fetch("http://127.0.0.1:8000/api/v1/users/", {
    method: "POST",
    body: {
      username: email.value,
      password: password1.value,
    },
  });
}
</script>
