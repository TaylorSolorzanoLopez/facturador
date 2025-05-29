<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';
defineProps({ clientes: Array });
</script>

<template>
    <Head title="Clientes" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="text-xl font-semibold text-gray-800 dark:text-gray-200">
                Clientes
            </h2>
        </template>

        <div class="p-6">
            <Link href="/cliente/create" class="mb-4 inline-block bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700">
                Nuevo Cliente
            </Link>

            <table class="w-full text-left border-collapse">
                <thead>
                    <tr>
                        <th class="border px-4 py-2">Nombre</th>
                        <th class="border px-4 py-2">Correo</th>
                        <th class="border px-4 py-2">Teléfono</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="cliente in clientes" :key="cliente.id">
                        <td class="border px-4 py-2">{{ cliente.nombre }}</td>
                        <td class="border px-4 py-2">{{ cliente.correo }}</td>
                        <td class="border px-4 py-2">{{ cliente.telefono }}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </AuthenticatedLayout>
</template>
