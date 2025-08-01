<template>
  <aside class="bg-white p-4 border rounded shadow space-y-4 w-full">
    <h2 class="text-lg font-semibold">Bộ lọc tìm kiếm</h2>

    <!-- Loại bất động sản -->
    <div>
      <label class="block text-sm font-medium mb-1">Loại bất động sản</label>
      <select v-model="filters.type" class="w-full border rounded px-2 py-1">
        <option value="">Tất cả</option>
        <option>Nhà riêng</option>
        <option>Chung cư</option>
        <option>Biệt thự</option>
        <option>Đất nền</option>
      </select>
    </div>

    <!-- Tỉnh/Thành phố -->
    <div>
      <label class="block text-sm font-medium mb-1">Tỉnh/Thành phố</label>
      <select v-model="filters.city" class="w-full border rounded px-2 py-1">
        <option value="">Tất cả</option>
        <option>Hà Nội</option>
        <option>TP.HCM</option>
        <option>Đà Nẵng</option>
        <option>Cần Thơ</option>
      </select>
    </div>

    <!-- Mức giá -->
    <div>
      <label class="block text-sm font-medium mb-1">Khoảng giá (tỷ VNĐ)</label>
      <div class="flex gap-2">
        <input
          v-model="filters.priceMin"
          type="number"
          min="0"
          class="w-1/2 border rounded px-2 py-1"
          placeholder="Từ"
        />
        <input
          v-model="filters.priceMax"
          type="number"
          min="0"
          class="w-1/2 border rounded px-2 py-1"
          placeholder="Đến"
        />
      </div>
    </div>

    <!-- Diện tích -->
    <div>
      <label class="block text-sm font-medium mb-1">Diện tích (m²)</label>
      <div class="flex gap-2">
        <input
          v-model="filters.areaMin"
          type="number"
          min="0"
          class="w-1/2 border rounded px-2 py-1"
          placeholder="Từ"
        />
        <input
          v-model="filters.areaMax"
          type="number"
          min="0"
          class="w-1/2 border rounded px-2 py-1"
          placeholder="Đến"
        />
      </div>
    </div>

    <!-- Số phòng ngủ -->
    <div>
      <label class="block text-sm font-medium mb-1">Số phòng ngủ</label>
      <select
        v-model="filters.bedrooms"
        class="w-full border rounded px-2 py-1"
      >
        <option value="">Tất cả</option>
        <option>1+</option>
        <option>2+</option>
        <option>3+</option>
        <option>4+</option>
      </select>
    </div>

    <!-- Nút tìm kiếm -->
    <button
      class="w-full bg-blue-600 text-white py-2 rounded hover:bg-blue-700 transition"
      @click="applyFilter"
    >
      Tìm kiếm
    </button>
  </aside>
</template>

<script setup>
import { reactive } from "vue";

const filters = reactive({
  type: "",
  city: "",
  priceMin: "",
  priceMax: "",
  areaMin: "",
  areaMax: "",
  bedrooms: "",
});

const applyFilter = () => {
  console.log("Lọc với:", filters);
  // Gửi filters đến API hoặc sự kiện cha emit
};
</script>
