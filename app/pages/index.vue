<template>
  <div>
    <HeroSection />
    <div
      class="container mx-auto mt-6 px-4 grid grid-cols-1 md:grid-cols-4 gap-4"
    >
      <FilterSidebar class="hidden md:block md:col-span-1" />
      <div class="col-span-1 md:col-span-3">
        <h1 class="text-2xl font-semibold mb-4">Nhà đất bán</h1>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <PropertyCard v-for="item in 6" :key="item" />
        </div>
      </div>
    </div>

    <LandSection />

    <RealEstateSection />
  </div>
</template>

<script setup>
import PropertyCard from "./PropertyCard.vue";
import HeroSection from "@/components/HeroSection.vue";
import FilterSidebar from "./FilterSidebar.vue";
import LandSection from "./LandSection.vue";
import RealEstateSection from "./RealEstateSection.vue";
</script>
