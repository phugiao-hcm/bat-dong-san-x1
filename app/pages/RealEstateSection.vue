<template>
  <section class="bg-gray-100 py-10">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold mb-6 text-center text-gray-800">
        Nhà Bán & Nhà Thuê
      </h2>

      <div class="grid md:grid-cols-2 gap-8">
        <!-- Nhà Bán -->
        <div class="bg-white p-6 rounded-xl shadow hover:shadow-lg transition">
          <h3 class="text-xl font-semibold text-blue-600 mb-4">Nhà Bán</h3>
          <p class="text-gray-600 mb-4">
            Khám phá những căn nhà đang rao bán với giá hấp dẫn tại các khu vực
            hot nhất hiện nay.
          </p>
          <NuxtLink
            to="/nha-ban"
            class="inline-block bg-blue-500 text-white px-5 py-2 rounded hover:bg-blue-600 transition"
          >
            Xem danh sách
          </NuxtLink>
        </div>

        <!-- Nhà Thuê -->
        <div class="bg-white p-6 rounded-xl shadow hover:shadow-lg transition">
          <h3 class="text-xl font-semibold text-green-600 mb-4">Nhà Thuê</h3>
          <p class="text-gray-600 mb-4">
            Tìm nhà cho thuê với giá hợp lý, vị trí thuận tiện, phù hợp cho cá
            nhân & gia đình.
          </p>
          <NuxtLink
            to="/nha-thue"
            class="inline-block bg-green-500 text-white px-5 py-2 rounded hover:bg-green-600 transition"
          >
            Xem danh sách
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>
