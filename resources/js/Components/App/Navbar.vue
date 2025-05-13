<script setup>
import SvgIcon from 'vue3-icon'
import {mdiAccountCircle, mdiMessageBadge, mdiMagnify, mdiBrightness6, mdiBrightness4} from "@mdi/js";
import {ref} from "vue";


const isLightMode = ref(false);
const toggleLightMode = () => {
    isLightMode.value = !isLightMode.value;
};
</script>

<template>
    <div class="ml-0 sm:ml-24 md:ml-64 py-4 bg-[#030303]">
        <nav class="grid grid-cols-2 px-4">
            <div class="flex items-center gap-2 py-1">
                <svg-icon type="mdi" :path="mdiMagnify" class="relative left-10 text-slate-500"></svg-icon>
                <input class="py-2 w-[400px] rounded-lg pl-9" placeholder="Search.."/>
            </div>
            <div class="flex gap-2 justify-end items-center">
                <svg-icon v-if="isLightMode" @click="toggleLightMode" type="mdi" :path="mdiBrightness6" :size="32"
                          style="color: yellow; cursor: pointer"></svg-icon>
                <svg-icon v-else @click="toggleLightMode" type="mdi" :path="mdiBrightness4" :size="32"
                          style="color: white;cursor: pointer"></svg-icon>
                <svg-icon type="mdi" :path="mdiMessageBadge" :size="32" style="color: white"
                          class="relative top-0.5 cursor-pointer"></svg-icon>
                <svg-icon type="mdi" :path="mdiAccountCircle" :size="32" style="color: white"></svg-icon>
            </div>
        </nav>
    </div>
</template>


