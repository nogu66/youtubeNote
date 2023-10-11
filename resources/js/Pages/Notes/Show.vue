<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import SvgIcon from "@jamescoyle/vue-icon";
import { mdiMagnify, mdiPlus } from "@mdi/js";

const props = defineProps({
    note: Array,
});
</script>

<template>
    <Head title="Detail" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Detail
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-8xl sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">
                        <section class="text-gray-600 body-font relative">
                            <div class="container px-5 py-24 mx-auto">
                                <div
                                    class="flex flex-col text-center w-full mb-12"
                                >
                                    <h1
                                        class="sm:text-3xl text-2xl font-medium title-font mb-4 text-gray-900"
                                    >
                                        Detail
                                    </h1>
                                </div>
                                <div class="w-full mx-auto">
                                    <div class="flex flex-row flex-wrap -m-2">
                                        <div class="p-2 w-full">
                                            <div class="relative">
                                                <label
                                                    for="name"
                                                    class="leading-7 text-sm text-gray-600"
                                                    >URL</label
                                                >
                                                <div
                                                    type="text"
                                                    id="name"
                                                    name="name"
                                                    class="flex flex-row flex-wraw-full h-fit bg-gray-100 bg-opacity-50 rounded border border-gray-300 focus:border-indigo-500 focus:bg-white focus:ring-2 focus:ring-indigo-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out"
                                                >
                                                    {{ props.note.url }}
                                                </div>
                                            </div>
                                        </div>
                                        <div class="p-2 w-full">
                                            <div class="relative">
                                                <label
                                                    for="email"
                                                    class="leading-7 text-sm text-gray-600"
                                                    >タイトル</label
                                                >
                                                <div
                                                    type="email"
                                                    id="email"
                                                    name="email"
                                                    class="w-full h-fit bg-gray-100 bg-opacity-50 rounded border border-gray-300 focus:border-indigo-500 focus:bg-white focus:ring-2 focus:ring-indigo-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out"
                                                >
                                                    {{ props.note.title }}
                                                </div>
                                            </div>
                                        </div>
                                        <div class="p-2 w-full">
                                            <div class="relative">
                                                <label
                                                    for="message"
                                                    class="leading-7 text-sm text-gray-600"
                                                    >Message</label
                                                >
                                                <div
                                                    id="message"
                                                    name="message"
                                                    class="w-full h-fit bg-gray-100 bg-opacity-50 rounded border border-gray-300 focus:border-indigo-500 focus:bg-white focus:ring-2 focus:ring-indigo-200 h-32 text-base outline-none text-gray-700 py-1 px-3 resize-none leading-6 transition-colors duration-200 ease-in-out"
                                                >
                                                    {{ props.note.note }}
                                                </div>
                                            </div>
                                        </div>

                                        <div class="p-2 w-full">
                                            <button
                                                class="flex mx-auto text-white bg-indigo-500 border-0 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg"
                                            >
                                                Edit
                                            </button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </section>
                        GitHub
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
