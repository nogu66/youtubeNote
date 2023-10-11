<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import SvgIcon from "@jamescoyle/vue-icon";
import { mdiMagnify, mdiPlus } from "@mdi/js";
// import FlashMessage from "@/Components/FlashMessage.vue";

const props = defineProps({
    notes: Array,
});
</script>

<template>
    <Head title="Home" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Home
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-8xl sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">
                        <section class="text-gray-600 body-font">
                            <div class="container px-5 py-24 mx-auto">
                                <div
                                    class="flex flex-col text-center w-full mb-8"
                                >
                                    <h1
                                        class="sm:text-4xl text-3xl font-medium title-font text-gray-900"
                                    >
                                        YouTubeNote
                                    </h1>
                                </div>

                                <div
                                    class="flex mb-5 w-full mx-auto items-center"
                                >
                                    <input
                                        type="text"
                                        name="search"
                                        v-model="search"
                                        class="w-4/6 mr-4"
                                    />
                                    <button
                                        class="flex items-center justify-center w-1/6 bg-blue-300 text-white py-3 px-10 mr-4 rounded"
                                        @click="searchCustomers"
                                    >
                                        <span class="hidden sm:block"
                                            >検索</span
                                        >
                                        <span class="block sm:hidden">
                                            <svg-icon
                                                type="mdi"
                                                :path="mdiMagnify"
                                            ></svg-icon>
                                        </span>
                                    </button>
                                    <Link
                                        as="button"
                                        :href="route('notes.create')"
                                        class="flex items-center justify-center w-1/6 text-white bg-indigo-500 border-0 py-3 px-10 focus:outline-none hover:bg-indigo-600 rounded"
                                    >
                                        <span class="hidden sm:block">Add</span>
                                        <span class="block sm:hidden">
                                            <svg-icon
                                                type="mdi"
                                                :path="mdiPlus"
                                            ></svg-icon>
                                        </span>
                                    </Link>
                                </div>

                                <div class="flex flex-wrap -m-4">
                                    <div
                                        v-for="note in props.notes"
                                        :key="note.id"
                                        class="p-4 w-full lg:w-1/3"
                                    >
                                        <div
                                            class="h-full bg-gray-100 bg-opacity-75 px-8 pt-16 pb-24 rounded-lg overflow-hidden text-center relative"
                                        >
                                            <h1
                                                class="title-font sm:text-2xl text-xl font-medium text-gray-900 mb-3 truncate"
                                            >
                                                {{ note.title }}
                                            </h1>
                                            <h2
                                                class="tracking-widest text-xs title-font font-medium text-gray-400 mb-1 truncate"
                                            >
                                                {{ note.url }}
                                            </h2>
                                            <p
                                                class="leading-relaxed mb-3 truncate"
                                            >
                                                {{ note.note }}
                                            </p>
                                            <Link
                                                :href="
                                                    route('notes.show', {
                                                        note: note,
                                                    })
                                                "
                                                class="text-indigo-500 inline-flex items-center"
                                                >Learn More
                                                <svg
                                                    class="w-4 h-4 ml-2"
                                                    viewBox="0 0 24 24"
                                                    stroke="currentColor"
                                                    stroke-width="2"
                                                    fill="none"
                                                    stroke-linecap="round"
                                                    stroke-linejoin="round"
                                                >
                                                    <path d="M5 12h14"></path>
                                                    <path
                                                        d="M12 5l7 7-7 7"
                                                    ></path>
                                                </svg>
                                            </Link>
                                            <div
                                                class="text-center mt-2 leading-none flex justify-center absolute bottom-0 left-0 w-full py-4"
                                            ></div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </section>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
