<script setup>
const props = defineProps({
  my: Boolean,
  job: Object,
});
</script>

<template>
  <div class="p-6 flex items-center justify-between bg-gray-100 rounded-xl">
    <div>
      <h3 class="mb-2 text-xl font-semibold">{{ job.title }}</h3>
      <p class="text-gray-600">{{ job.company_name }}</p>
    </div>
    <div>
      <p class="mb-2">{{ job.position_location }}</p>
      <p>{{ job.position_salary }}</p>
    </div>
    <div>
      <p>{{ job.created_at_formatted }}</p>
    </div>
    <div class="space-x-1">
      <nuxt-link
        :to="{ name: 'browse-id', params: { id: job.id } }"
        class="py-4 px-6 bg-teal-700 text-white rounded-xl"
        >Details</nuxt-link
      >
      <nuxt-link
        v-if="my"
        to="/browse/1"
        class="py-4 px-6 bg-cyan-700 text-white rounded-xl"
        >Edit</nuxt-link
      >
      <nuxt-link
        v-if="my"
        to="/browse/1"
        class="py-4 px-6 bg-rose-700 text-white rounded-xl"
        >Delete</nuxt-link
      >
    </div>
  </div>
</template>
