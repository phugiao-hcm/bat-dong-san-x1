<template>
    <div class="max-w-7xl mx-auto p-4">
        <!-- Swiper lớn -->
        <swiper
            :modules="[Navigation, Thumbs]"
            :thumbs="{ swiper: thumbsSwiper }"
            class="mb-4"
        >
            <swiper-slide v-for="(img, index) in images" :key="index">
                <img
                    :src="img"
                    class="rounded-lg w-full h-[400px] object-cover"
                />
            </swiper-slide>
        </swiper>

        <!-- Swiper thumbnail -->
        <swiper
            :modules="[Thumbs]"
            slides-per-view="5"
            space-between="10"
            @swiper="setThumbsSwiper"
            watchSlidesProgress
            class="mb-8"
        >
            <swiper-slide
                v-for="(img, index) in images"
                :key="'thumb-' + index"
                class="cursor-pointer"
            >
                <img
                    :src="img"
                    class="rounded-md h-20 w-full object-cover border"
                />
            </swiper-slide>
        </swiper>

        <!-- Thông tin chi tiết -->
        <div class="grid md:grid-cols-2 gap-8">
            <div>
                <h1 class="text-2xl font-bold mb-2">
                    Quỹ căn Studio - 3PN Vinhomes
                </h1>
                <p class="text-gray-600 mb-4">
                    View đẹp, giá rẻ, pháp lý rõ ràng.
                </p>
                <ul class="space-y-2">
                    <li><strong>Giá:</strong> 3,05 tỷ (~51,7 triệu/m²)</li>
                    <li><strong>Diện tích:</strong> 59 m²</li>
                    <li><strong>Phòng ngủ:</strong> 2 PN</li>
                    <li>
                        <strong>Vị trí:</strong> Dự án Vinhomes Ocean Park, Gia
                        Lâm, Hà Nội
                    </li>
                </ul>
            </div>

            <div class="border p-4 rounded-lg shadow-sm">
                <h2 class="text-lg font-semibold mb-4">Liên hệ môi giới</h2>
                <div class="flex items-center gap-4">
                    <img
                        src="https://via.placeholder.com/60"
                        alt="avatar"
                        class="w-16 h-16 rounded-full"
                    />
                    <div>
                        <p class="font-bold">Nguyễn Thị Yến Hoa</p>
                        <p class="text-sm text-gray-500">9 năm kinh nghiệm</p>
                        <p class="text-sm text-gray-500">111 tin đăng</p>
                    </div>
                </div>
                <button
                    class="mt-4 bg-green-600 text-white w-full py-2 rounded-lg hover:bg-green-700 transition"
                >
                    0986 784 xxx - Hiện số
                </button>
            </div>
        </div>
    </div>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Thumbs } from "swiper/modules";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/thumbs";
import { ref } from "vue";

const thumbsSwiper = ref(null);
const setThumbsSwiper = (swiper) => {
    thumbsSwiper.value = swiper;
};

const images = [
    "/images/1.png",
    "/images/2.png",
    "/images/3.png",
    "/images/4.png",
    "/images/5.png",
    "/images/6.png",
    "/images/7.png",
];
</script>

<style scoped>
.swiper-slide-thumb-active {
    border: 2px solid #22c55e;
}
</style>
