<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';

console.log('hola amiguitos! como estan!');
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800 dark:text-gray-200">
                Dashboard
            </h2>
        </template>

        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg dark:bg-gray-800">
                    <div class="p-6 text-gray-900 dark:text-gray-100">
                        You're logged in!
                    </div>
                    <!-- ✅ Nuevo botón aquí -->
                    <div class="p-6">
                        <button
                            @click="handleClick"
                            class="px-4 py-2 font-semibold text-white bg-blue-600 rounded hover:bg-blue-700"
                        >
                            Haz clic aquí
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<script>
export default {
    methods: {
        handleClick() {
            alert('¡Hola! Has hecho clic en el botón.');
        }
    }
}
</script>
