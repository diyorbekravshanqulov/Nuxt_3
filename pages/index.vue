<template>
  <div class="container">
    <p class="text-4xl text-center">Home</p>
    <p
      class="text-xl mt-5 text-center cursor-pointer"
      @click="router.push('/products')"
    >
      products
    </p>
  </div>
</template>

<script setup>
const router = useRouter();
</script>
