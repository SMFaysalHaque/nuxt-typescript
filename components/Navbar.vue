<template>
    <div class="w-full bg-blue-100 mb-2">
        <div class="w-6/12 h-16 flex justify-between items-center gap-x-3 mx-auto">
            <div>
                <NuxtLink to="/" class="border px-10 py-2 font-medium hover:bg-blue-400 transform duration-300">Division</NuxtLink>
                <NuxtLink to="/restaurant" class="border px-10 py-2 font-medium hover:bg-blue-400 transform duration-300">Restaurant</NuxtLink>
                <NuxtLink to="/contact" class="border px-10 py-2 font-medium hover:bg-blue-400 transform duration-300">Contact Us</NuxtLink>
            </div>
            <div>
                <NuxtLink to="/" class="font-bold text-3xl text-blue-700 hover:text-blue-500 transform duration-500 ease-out">Nuxt3/TypeScript</NuxtLink>     
            </div>
        </div>
    </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>