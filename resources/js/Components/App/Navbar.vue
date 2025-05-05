<script setup>
defineProps({
    listMenu: {
        type: Array,
        required: true,
    }
})
</script>

<template>
    <div>
        <nav class="flex items-center justify-between px-4">
            <div class="flex gap-8 items-center">
                <a href="/" class="text-lg font-bold">CostShift</a>
                <div class="hidden md:flex space-x-4">
                    <a v-for="(menu, index) in listMenu" :key="index"
                       :href="menu.path" class="text-gray-700 hover:text-gray-900">
                        {{ menu.name }}
                    </a>
                </div>
            </div>
            <div class="hidden md:block">
                <button class="py-2 px-6 font-bold border border-black rounded-full">
                    Get Started
                </button>
            </div>
            <div class="md:hidden">
                <button @click="$emit('toggle-menu')" class="text-gray-700 focus:outline-none">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2"
                         stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16m-7 6h7"/>
                    </svg>
                </button>
            </div>
        </nav>
    </div>
</template>


