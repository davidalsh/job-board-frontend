<script setup>
const userStore = useUserStore();
onMounted(() => {
  userStore.initStore();
});
</script>

<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>
