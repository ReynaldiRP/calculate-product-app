<script setup>
import SvgIcon from 'vue3-icon'
import {mdiHome, mdiPackage, mdiGrain} from "@mdi/js";

const menus = [
    {name: 'Home', path: '/about', icon: mdiHome},
    {name: 'Products', path: '/product', icon: mdiPackage},
    {name: 'Ingredients', path: '/ingredients', icon: mdiGrain},
];
</script>

<template>
    <div>
        <nav class="mt-4">
            <ul class="flex flex-col gap-1">
                <template v-for="(menu, index) in menus" :key="index">
                    <li class="block md:flex md:items-center md:gap-2 p-2 rounded-lg cursor-pointer text-white hover:bg-slate-300 hover:text-[#030303]">
                        <svg-icon type="mdi" :path="menu.icon" class="mx-auto md:mx-0" :size="32"></svg-icon>
                        <a :href="menu.path" class="hidden md:block">{{ menu.name }}</a>
                    </li>
                </template>
            </ul>
        </nav>
    </div>
</template>

<style scoped>

</style>
