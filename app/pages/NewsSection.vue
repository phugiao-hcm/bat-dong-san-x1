<template>
    <section class="bg-gray-50 py-12">
        <div class="max-w-7xl mx-auto px-4">
            <h2 class="text-2xl font-semibold mb-6">Tin tức bất động sản</h2>
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                <article
                    v-for="(news, index) in newsList"
                    :key="index"
                    class="bg-white rounded shadow hover:shadow-lg transition overflow-hidden"
                >
                    <img
                        :src="news.image"
                        :alt="news.title"
                        class="w-full h-48 object-cover"
                    />
                    <div class="p-4">
                        <h3
                            class="text-lg font-bold text-blue-700 mb-2 hover:text-blue-900 cursor-pointer"
                        >
                            {{ news.title }}
                        </h3>
                        <p class="text-xs text-gray-500 mb-3">
                            {{ news.date }}
                        </p>
                        <p class="text-gray-700 text-sm line-clamp-3">
                            {{ news.summary }}
                        </p>
                    </div>
                </article>
            </div>
        </div>
    </section>
</template>


<script setup>
const newsList = [
    {
        title: "Giá đất Phú Giáo tăng mạnh trong năm 2025",
        date: "01/08/2025",
        image: "images/1.png",
        summary:
            "Giá đất tại huyện Phú Giáo đang có xu hướng tăng mạnh nhờ sự phát triển hạ tầng và thu hút đầu tư từ các dự án lớn...",
    },
    {
        title: "Kinh nghiệm đầu tư bất động sản hiệu quả",
        date: "28/07/2025",
        image: "images/2.png",
        summary:
            "Để đầu tư bất động sản hiệu quả, nhà đầu tư cần nắm bắt được thị trường, chọn vị trí phù hợp và đánh giá đúng tiềm năng phát triển...",
    },
    {
        title: "Chính sách mới hỗ trợ nhà đầu tư bất động sản tại Bình Dương",
        date: "25/07/2025",
        image: "images/3.png",
        summary:
            "Chính quyền Bình Dương vừa ban hành các chính sách hỗ trợ phát triển bất động sản, tạo điều kiện thuận lợi cho nhà đầu tư...",
    },
];
</script>

<style scoped>
/* Giới hạn số dòng mô tả trong card */
.line-clamp-3 {
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
}
</style>
