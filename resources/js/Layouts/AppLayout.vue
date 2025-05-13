<script setup>
import Sidebar from "@/Components/App/Sidebar.vue";
import Navbar from "@/Components/App/Navbar.vue";
</script>

<template>
    <div>
        <Sidebar/>
        <section class="bg-[#13090A] bg-opacity-90 ">
            <header>
                <Navbar/>
            </header>
            <main class="ml-0 sm:ml-24 md:ml-64 flex flex-col items-center justify-center min-h-screen">
                <slot></slot>
            </main>
            <footer class="ml-0 sm:ml-24 md:ml-64 pb-4">
                <p class="text-center text-gray-500 text-sm">
                    &copy; {{ new Date().getFullYear() }} Your Company. All rights reserved.
                </p>
            </footer>
        </section>
    </div>
</template>


