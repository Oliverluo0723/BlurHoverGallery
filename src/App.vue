<script setup lang="ts">
import { ref } from "vue";
import img1 from "@/assets/images/img1.jpg";
import img2 from "@/assets/images/img2.jpg";
import img3 from "@/assets/images/img3.png";
import img4 from "@/assets/images/img4.png";
import img5 from "@/assets/images/img5.jpg";

const images = [img1, img2, img3, img4, img5];
const imageRef = ref();

const companyNames = [
    "JUMP FACTORY",
    "ADCKER",
    "JOCHI LABS",
    "MAIANNA",
    "NEWOL",
    "FUTURE AGENCY",
    "BUILT BY ROSE SWIMW",
    "HYBIRD CREATIVED",
    "JUMP FACTORY",
];

const handleMouseEnter = (index: number): void => {
    if (images[index]) {
        imageRef.value = images[index];
    } else {
        imageRef.value = null;
    }
};

const handleMouseLeave = (): void => {
    imageRef.value = null;
};
</script>
<template>
    <header class="w-full h-24 px-4 flex-between">
        <h2 class="cursor-pointer hover-blur">emele</h2>
        <nav>
            <ul class="flex gap-2 cursor-pointer">
                <li class="hover-blur">List /</li>
                <li class="hover-blur">Grid /</li>
                <li class="hover-blur">Gallery</li>
            </ul>
        </nav>
        <h2 class="cursor-pointer hover-blur">studio lab</h2>
    </header>
    <section>
        <h1
            class="w-full text-center hover-blur cursor-pointer"
            v-for="(value, index) in companyNames"
            :key="index"
            @mouseenter="handleMouseEnter(index)"
            @mouseleave="handleMouseLeave"
        >
            {{ value }}
        </h1>
    </section>
    <div class="w-80 aspect-square fixed left-1/6 lg:left-9/12 top-7/12">
        <img v-show="imageRef" :src="imageRef ?? undefined" alt="圖片" />
    </div>
</template>
<style scoped></style>
