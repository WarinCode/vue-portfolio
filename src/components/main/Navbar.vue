<script setup lang="ts">
import { ref } from "vue";
import NavLink from "../NavLink.vue";
import { navItemData } from "@/constants";
import { NavItemData } from "@/types";
import Icon from "../Icon.vue";
import MobileMenu from "../MobileMenu.vue";

const navItems = ref<NavItemData[]>(navItemData);
const isOpen = ref<boolean>(false);

const handleOpen = (): void => {
    isOpen.value = !isOpen.value;
}

</script>

<template>
    <nav class="flex flex-col p-6 w-full sticky -top-1 h-20 z-50 px-28 backdrop-blur-lg max-[430px]:px-12"
        :class="{ 'h-max': isOpen }">
        <div class="flex items-center justify-between">
            <div class="flex items-center w-1/2 cursor-default max-[430px]:w-full">
                <img src="/assets/logo.svg" alt="vue-logo"
                    class="w-12 h-12 transition delay-100 ease-in-out max-[430px]:w-10 max-[430px]:h-10" />
                <h4 class="capitalize ms-3 text-2xl text-secondary tracking-wide max-[430px]:text-xl">
                    vue portfolio
                </h4>
            </div>
            <div class="hidden max-[430px]:block" @click="handleOpen">
                <Icon icon-path="assets/svgs/bars-solid.svg" classname="h-6 w-6" />
            </div>
            <ul class="flex items-center justify-evenly w-1/2 cursor-pointer tracking-wide max-[430px]:hidden">
                <NavLink v-for="item of navItems" :href="item.href" :text="item.text" />
            </ul>
        </div>
        <MobileMenu v-if="isOpen" />
    </nav>
</template>