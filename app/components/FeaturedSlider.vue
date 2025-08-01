<template>
  <section class="py-10 px-4">
    <div class="max-w-7xl mx-auto relative">
      <Swiper
        :modules="[Navigation, Autoplay, Pagination]"
        :slides-per-view="1.3"
        :space-between="16"
        :loop="false"
        :autoplay="{ delay: 4000 }"
        :pagination="{ clickable: true }"
        :navigation="{
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        }"
        :breakpoints="breakpoints"
        class="group"
      >
        <SwiperSlide v-for="(item, index) in products" :key="index">
          <div
            class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-300"
          >
            <img
              :src="item.image"
              :alt="item.name"
              class="w-full h-60 object-cover"
            />
            <div class="p-4">
              <h3 class="text-lg font-semibold">{{ item.name }}</h3>
              <p class="text-pink-600 font-bold mt-2">{{ item.price }}</p>
            </div>
          </div>
        </SwiperSlide>

        <!-- Nút điều hướng -->
        <div
          class="swiper-button-prev hidden md:flex absolute top-1/2 left-0 transform -translate-y-1/2 z-10 text-gray-800 hover:text-black"
        ></div>
        <div
          class="swiper-button-next hidden md:flex absolute top-1/2 right-0 transform -translate-y-1/2 z-10 text-gray-800 hover:text-black"
        ></div>
      </Swiper>
    </div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Autoplay, Pagination } from "swiper/modules";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

const products = [
  { name: "Áo Thun Trẻ Trung", price: "350.000đ", image: "/images/1.png" },
  { name: "Đầm Công Sở", price: "520.000đ", image: "/images/2.png" },
  { name: "Áo Khoác Nữ Tính", price: "470.000đ", image: "/images/3.png" },
  { name: "Quần Jeans Cá Tính", price: "420.000đ", image: "/images/4.png" },
  { name: "Chân Váy Dịu Dàng", price: "390.000đ", image: "/images/5.png" },
];

const breakpoints = {
  640: {
    slidesPerView: 1.5,
    spaceBetween: 16,
  },
  1024: {
    slidesPerView: 3.2,
    spaceBetween: 20,
  },
};
</script>

