<template>
    <section class="py-12 bg-gray-100">
        <div class="max-w-7xl mx-auto px-4">
            <!-- Title -->
            <h1
                class="text-4xl font-extrabold text-blue-700 mb-3 relative inline-block"
            >
                Bất động sản nổi bật
                <span
                    class="absolute left-0 -bottom-1 w-20 h-1 bg-blue-500 rounded-full"
                ></span>
            </h1>
            <p class="text-gray-600 mb-8 max-w-xl">
                Tìm kiếm các bất động sản nhà đất đẹp và phù hợp nhất với bạn
                tại Phú Giáo và các khu vực lân cận.
            </p>

            <!-- Tabs -->
            <div class="flex gap-4 mb-8">
                <button
                    v-for="tab in tabs"
                    :key="tab.value"
                    @click="activeTab = tab.value"
                    :class="[
                        'px-4 py-2 rounded-full font-medium border transition-all duration-200',
                        activeTab === tab.value
                            ? 'bg-blue-600 text-white border-blue-600'
                            : 'bg-white text-gray-700 border-gray-300 hover:bg-blue-50',
                    ]"
                >
                    {{ tab.label }}
                </button>
            </div>

            <!-- Listings -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                <div
                    v-for="(item, index) in filteredList"
                    :key="index"
                    class="bg-white rounded-xl shadow hover:shadow-lg transition-shadow overflow-hidden"
                >
                    <img
                        :src="item.image"
                        alt="property"
                        class="w-full h-48 object-cover"
                    />
                    <div class="p-4">
                        <h3 class="font-semibold text-lg text-gray-800">
                            {{ item.title }}
                        </h3>
                        <p class="text-gray-600 mt-1 text-sm">
                            {{ item.address }}
                        </p>
                        <p class="text-blue-600 font-bold mt-3">
                            {{ item.price }}
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, computed } from "vue";

const tabs = ref([
    { label: "Tất cả", value: "all" },
    { label: "Căn hộ", value: "apartment" },
    { label: "Nhà đất", value: "house" },
    { label: "Đất nền", value: "land" },
]);

const activeTab = ref("all");

const listings = ref([
    {
        title: "Căn hộ cao cấp trung tâm thành phố",
        address: "Quận 1, TP. HCM",
        price: "3.5 tỷ",
        type: "apartment",
        image: "images/1.png",
    },
    {
        title: "Nhà phố rộng rãi, khu dân cư an ninh",
        address: "Bình Dương",
        price: "5 tỷ",
        type: "house",
        image: "images/2.png",
    },
    {
        title: "Đất nền sổ đỏ, tiện xây dựng tự do",
        address: "Phú Giáo, Bình Dương",
        price: "1.2 tỷ",
        type: "land",
        image: "images/3.png",
    },
    {
        title: "Căn hộ studio hiện đại, giá hợp lý",
        address: "Thủ Đức, TP. HCM",
        price: "2.1 tỷ",
        type: "apartment",
        image: "images/4.png",
    },
    {
        title: "Căn hộ studio hiện đại, giá hợp lý",
        address: "Thủ Đức, TP. HCM",
        price: "2.1 tỷ",
        type: "apartment",
        image: "images/5.png",
    },
    {
        title: "Căn hộ studio hiện đại, giá hợp lý",
        address: "Thủ Đức, TP. HCM",
        price: "2.1 tỷ",
        type: "apartment",
        image: "images/6.png",
    },
]);

const filteredList = computed(() => {
    if (activeTab.value === "all") return listings.value;
    return listings.value.filter((item) => item.type === activeTab.value);
});
</script>
