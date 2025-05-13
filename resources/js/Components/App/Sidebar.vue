<script setup>
import {computed, onMounted, onUnmounted, ref} from 'vue';
import SidebarItem from "@/Components/App/SidebarItem.vue";

const currentWindowWidth = ref(window.innerWidth);
const isMobile = computed(() => {
    return currentWindowWidth.value <= 640;
});


onMounted(
    () => {
        window.addEventListener('resize', () => {
            currentWindowWidth.value = window.innerWidth;
        });
    }
)

onUnmounted(() => {
        window.removeEventListener('resize', () => {
            currentWindowWidth.value = window.innerWidth;
        });
    }
)
</script>

<template>
    <div>
        <aside
            class="bg-[#030303] transition-all duration-300 ease-in-out fixed top-0 left-0 w-24 md:w-64 h-screen rounded-l-2xl p-4"
            :class="isMobile ? '-translate-x-full' : 'translate-x-0'"
        >
            <section class="flex gap-2 items-center">
                <div class="w-14 rounded-xl mx-auto md:mx-0">
                    <img src="https://picsum.photos/200" alt="Logo" class="rounded-xl"/>
                </div>
                <h1 class="text-white text-xl font-sans font-bold text-center hidden md:block">
                    CostShift</h1>
            </section>
            <hr class="mt-4 border-2 border-white border-opacity-50 rounded-lg"/>
            <SidebarItem/>
        </aside>
    </div>
</template>

<style scoped>

</style>
