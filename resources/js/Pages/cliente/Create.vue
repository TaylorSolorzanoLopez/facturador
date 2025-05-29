<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, useForm } from '@inertiajs/vue3';

const form = useForm({
    nombre: '',
    correo: '',
    telefono: ''
});

function submit() {
    form.post('/cliente/store');
}
</script>

<template>
    <Head title="Registrar Cliente" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="text-xl font-semibold text-gray-800 dark:text-gray-200">
                Registrar Cliente
            </h2>
        </template>

        <div class="p-6 max-w-md mx-auto">
            <form @submit.prevent="submit" class="space-y-4">
                <div>
                    <label class="block">Nombre</label>
                    <input v-model="form.nombre" type="text" class="w-full border rounded px-3 py-2" />
                    <div v-if="form.errors.nombre" class="text-red-600">{{ form.errors.nombre }}</div>
                </div>

                <div>
                    <label class="block">Correo</label>
                    <input v-model="form.correo" type="email" class="w-full border rounded px-3 py-2" />
                </div>

                <div>
                    <label class="block">Teléfono</label>
                    <input v-model="form.telefono" type="text" class="w-full border rounded px-3 py-2" />
                </div>

                <button type="submit" class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700">
                    Guardar
                </button>
            </form>
        </div>
    </AuthenticatedLayout>
</template>
