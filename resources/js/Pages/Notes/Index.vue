<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
// import FlashMessage from "@/Components/FlashMessage.vue";

const props = defineProps({
    notes: Array,
});

console.log(props.notes);
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Dashboard
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-8xl sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">
                        <section class="text-gray-600 body-font">
                            <div class="container py-24 mx-auto">
                                <!-- <FlashMessage /> -->
                                <div
                                    class="flex flex-col text-center w-full mb-8"
                                >
                                    <h1
                                        class="sm:text-4xl text-3xl font-medium title-font mb-2 text-gray-900"
                                    >
                                        YouTubeNote
                                    </h1>
                                </div>
                                <div class="flex pl-4 m-4 w-full mx-auto">
                                    <Link
                                        as="button"
                                        :href="route('notes.create')"
                                        class="flex ml-auto text-white bg-indigo-500 border-0 py-2 px-6 focus:outline-none hover:bg-indigo-600 rounded"
                                    >
                                        Add Note
                                    </Link>
                                </div>
                                <div
                                    class="lg:w-full w-full mx-auto overflow-auto"
                                >
                                    <table
                                        class="table-fixed w-full text-left whitespace-no-wrap"
                                    >
                                        <thead>
                                            <tr>
                                                <th
                                                    class="px-4 py-3 title-font tracking-wider font-medium text-gray-900 text-sm bg-gray-100"
                                                >
                                                    Id
                                                </th>
                                                <th
                                                    class="px-4 py-3 title-font tracking-wider font-medium text-gray-900 text-sm bg-gray-100"
                                                >
                                                    タイトル
                                                </th>
                                                <th
                                                    class="px-4 py-3 title-font tracking-wider font-medium text-gray-900 text-sm bg-gray-100"
                                                >
                                                    URL
                                                </th>
                                                <th
                                                    class="px-4 py-3 title-font tracking-wider font-medium text-gray-900 text-sm bg-gray-100"
                                                >
                                                    メモ
                                                </th>
                                            </tr>
                                        </thead>
                                        <tbody>
                                            <tr
                                                v-for="note in props.notes"
                                                :key="note.id"
                                                class="h-35"
                                            >
                                                <td
                                                    class="w-1/5 px-4 py-3 text-right"
                                                >
                                                    <Link
                                                        :href="
                                                            route(
                                                                'notes.show',
                                                                { note: note }
                                                            )
                                                        "
                                                    >
                                                        {{ note.id }}
                                                    </Link>
                                                </td>
                                                <td
                                                    class="w-1/5 px-4 py-3 truncate"
                                                >
                                                    {{ note.title }}
                                                </td>
                                                <td
                                                    class="w-1/5 px-4 py-3 truncate"
                                                >
                                                    {{ note.url }}
                                                </td>
                                                <td
                                                    class="w-1/5 px-4 py-3 truncate"
                                                >
                                                    {{ note.note }}
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>
                                </div>
                            </div>
                        </section>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
