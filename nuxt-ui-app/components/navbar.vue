<template>
    <div class="w-screen">
        <div class="py-4 fixed top-0 left-0 w-full backdrop-blur-xl border-b dark:border-gray-700">
            <UContainer class="flex justify-between items-center">
                <ul class="flex gap-3 items-center">
                    <li class="text-xl font-semibold text-primary-500">
                        <ULink>
                            <h1>Histobox</h1>
                        </ULink>
                    </li>
                    <ul v-for="link in links" :key="link.name" class="flex items-center">
                        <li>
                            <ULink :href="link.url" target="_blank" class="flex items-center hover:text-primary-500 transition gap-2" rel="noopener noreferrer">
                                {{ link.name }}
                            </ULink>
                        </li>
                    </ul>
                </ul>
                <ul>
                    <li><ThemeSelector /></li>
                </ul>
            </UContainer>
        </div>
    </div>
</template>


<script setup>
const links = ref([
    { name: 'placeholder', url: '/'},
    { name: 'placeholder', url: '/'}
]);
</script>