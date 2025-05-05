<script setup>
import Navbar from "@/Components/App/Navbar.vue";

const listMenu = [
    {name: 'Home', path: '/about'},
    {name: 'Products', path: '/about'},
    {name: 'Ingredients', path: '/contact'},
];
</script>

<template>
    <div>
        <section class="container mx-auto px-4 py-8">
            <header>
                <Navbar :list-menu="listMenu"/>
            </header>

            <main class="flex flex-col items-center justify-center min-h-screen">
                <slot></slot>
            </main>


            <footer>
                <p class="text-center text-gray-500 text-sm">
                    &copy; {{ new Date().getFullYear() }} Your Company. All rights reserved.
                </p>
            </footer>
        </section>
    </div>
</template>


