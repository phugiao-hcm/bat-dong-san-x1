<template>
  <section class="py-10 bg-gray-100">
    <div class="container mx-auto px-4">
      <h2 class="text-2xl md:text-3xl font-bold mb-6">Bất động sản nổi bật</h2>

      <!-- Tabs -->
      <div class="flex gap-4 mb-6">
        <button
          class="px-4 py-2 font-medium rounded border"
          :class="{
            'bg-blue-600 text-white': activeTab === 'ban',
            'bg-white text-gray-700 border-gray-300': activeTab !== 'ban',
          }"
          @click="activeTab = 'ban'"
        >
          Đất bán
        </button>
        <button
          class="px-4 py-2 font-medium rounded border"
          :class="{
            'bg-blue-600 text-white': activeTab === 'thue',
            'bg-white text-gray-700 border-gray-300': activeTab !== 'thue',
          }"
          @click="activeTab = 'thue'"
        >
          Đất thuê
        </button>
      </div>

      <!-- Listings -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(item, index) in filteredList"
          :key="index"
          class="bg-white rounded-lg shadow-md overflow-hidden"
        >
          <img
            :src="item.image"
            alt="property"
            class="w-full h-48 object-cover"
          />
          <div class="p-4">
            <h3 class="font-semibold text-lg">{{ item.title }}</h3>
            <p class="text-gray-600 mt-1">{{ item.address }}</p>
            <p class="text-blue-600 font-bold mt-2">{{ item.price }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from "vue";

const activeTab = ref("ban");

const list = ref([
  {
    type: "ban",
    title: "Bán đất mặt tiền Quận 9, 120m²",
    address: "Đường Nguyễn Duy Trinh, TP. Thủ Đức",
    price: "3,2 tỷ",
    image: "/images/1.png",
  },
  {
    type: "ban",
    title: "Đất nền sổ hồng riêng",
    address: "Phường Hiệp Phú, TP. Thủ Đức",
    price: "2,8 tỷ",
    image: "/images/2.png",
  },
  {
    type: "thue",
    title: "Cho thuê đất trống 200m²",
    address: "Phường Tân Phú, Quận 7",
    price: "25 triệu/tháng",
    image: "/images/3.png",
  },
  {
    type: "thue",
    title: "Đất thuê mặt tiền 150m²",
    address: "Phường Bình Trưng Đông, Quận 2",
    price: "20 triệu/tháng",
    image: "/images/4.png",
  },
]);

const filteredList = computed(() =>
  list.value.filter((item) => item.type === activeTab.value)
);
</script>
