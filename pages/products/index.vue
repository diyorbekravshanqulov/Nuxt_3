<template>
  <div class="container">

  
    <div class="grid md:grid-cols-5 grid-cols-2 gap-[20px] justify-center">
      <router-link :to="`/products/${item.id}`"
        v-for="(item, i) in products"
        :key="i"
        class="mb-[30px] bg-k_oq shadow-xl pb-5 relative"
      >
        <img :src="item?.thumbnail" alt="" />
        <p
          class="font-normal text-[14px] leading-[16.41px] opacity-[70%] mx-[16px] mt-[10px] mb-[70px]"
        >
          {{ item?.brand }}
        </p>
        <p
          class="font-medium text-[16px] leading-[16px] mx-[16px] mt-[10px] absolute bottom-[75px] md:bottom-[90px]"
        >
          {{ item?.title }}
        </p>
        <p
          class="font-bold text-[14px] leading-[14px] mx-[16px] mt-[40px] text-k_asosiy line-through"
        >
          ${{ item?.discountPercentage }}
        </p>
        <p
          class="font-bold text-[20px] leading-[20px] mx-[16px] mt-[10px] text-k_moviy"
        >
          ${{ item?.price }}
        </p>
      </router-link>
    </div>
  </div>
</template>

<script setup>

const products = ref([]);

onMounted(async () => {
  try {
    const response = await fetch("https://dummyjson.com/products");
    const data = await response.json();
    products.value = data.products;
  } catch (error) {
    console.error("Error fetching products:", error);
  }
});

</script>
