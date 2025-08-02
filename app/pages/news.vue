<template>
    <div class="bg-gray-50 text-gray-800 min-h-screen">
        <!-- Hero Banner -->
        <section class="bg-white py-12 shadow">
            <div class="max-w-6xl mx-auto px-4 text-center">
                <h1 class="text-4xl font-bold mb-2">Tin Tức Bất Động Sản</h1>
                <p class="text-gray-600">
                    Cập nhật nhanh chóng những tin tức nóng hổi về thị trường
                    bất động sản Việt Nam
                </p>
            </div>
        </section>

        <!-- Tin tức nổi bật -->
        <section class="py-12">
            <div class="max-w-6xl mx-auto px-4">
                <h2 class="text-2xl font-semibold mb-6">Bài viết mới nhất</h2>
                <div class="grid gap-6 md:grid-cols-3">
                    <div
                        v-for="item in news"
                        :key="item.id"
                        class="bg-white rounded-xl shadow hover:shadow-lg transition p-4 flex flex-col"
                    >
                        <img
                            :src="item.image"
                            alt="Thumbnail"
                            class="w-full h-48 object-cover rounded-md mb-4"
                        />
                        <h3 class="text-lg font-bold mb-2">{{ item.title }}</h3>
                        <p class="text-gray-600 text-sm mb-4 line-clamp-3">
                            {{ item.description }}
                        </p>
                        <NuxtLink
                            :to="`/tin-tuc/${item.slug}`"
                            class="mt-auto text-blue-600 hover:underline text-sm font-medium"
                        >
                            Xem chi tiết →
                        </NuxtLink>
                    </div>
                </div>
                <!-- Pagination (giả lập) -->
            </div>
        </section>
    </div>
</template>

<script setup>
const news = [
    {
        id: 1,
        slug: "gia-dat-2025-ha-noi",
        title: "Giá đất Hà Nội tăng nhẹ đầu năm 2025",
        description:
            "Thị trường bất động sản thủ đô có dấu hiệu phục hồi sau thời gian trầm lắng. Các quận vùng ven chứng kiến mức tăng giá nhẹ...",
        image: "/images/1.png",
    },
    {
        id: 2,
        slug: "biet-thu-bien-da-nang",
        title: "Biệt thự biển Đà Nẵng thu hút giới đầu tư",
        description:
            "Khu vực ven biển Đà Nẵng tiếp tục là điểm nóng khi hàng loạt dự án biệt thự nghỉ dưỡng được tung ra với mức giá hấp dẫn...",
        image: "/images/2.png",
    },
    {
        id: 3,
        slug: "du-doan-thi-truong",
        title: "Dự đoán thị trường BĐS 6 tháng cuối năm",
        description:
            "Các chuyên gia nhận định phân khúc nhà ở bình dân và đất nền vẫn giữ vai trò chủ đạo trong 6 tháng cuối năm 2025...",
        image: "/images/3.png",
    },
];
</script>

<style scoped>
.line-clamp-3 {
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
}
</style>
