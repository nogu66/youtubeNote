<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';

const props = defineProps({
    notes: Array,
});
// const notes = [
//     {
//         id: 1,
//         url: 'https://www.youtube.com/watch?v=6KT9T73-Iik&list=WL&index=7',
//         title: 'Node.jsとexpressでチャットアプリケーションを作ってみよう！',
//         note: 'Node.jsとExpressdeをチャットアプリケーションを実装しながら学習できる',
//         created_at: '2023-08-12',
//         updated_at: '2023-09-28',
//     },
//     {
//         id: 2,
//         url: 'https://www.youtube.com/watch?v=ufitZF-SgN8&ab_channel=NHK',
//         title: 'NHK人物録『岡本太郎』～NHKアーカイブス～',
//         note: '岡本太郎の人物紹介をしている長さがちょうどよい動画',
//         created_at: '2023-09-28',
//         updated_at: '2023-09-28',
//     },
// ];

console.log(props.notes);
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="py-12">
            <div class="max-w-8xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <section class="text-gray-600 body-font">
                        <div class="container py-24 mx-auto">
                            <div class="flex flex-col text-center w-full mb-8">
                                <h1 class="sm:text-4xl text-3xl font-medium title-font mb-2 text-gray-900">
                                    YouTubeNote
                                </h1>
                            </div>
                            <div class="flex pl-4 m-4 lg:w-2/3 w-full mx-auto">
                                <button
                                    class="flex ml-auto text-white bg-indigo-500 border-0 py-2 px-6 focus:outline-none hover:bg-indigo-600 rounded"
                                >
                                    Add Note
                                </button>
                            </div>
                            <div class="lg:w-full w-full mx-auto overflow-auto">
                                <table class="table-auto w-full text-left whitespace-no-wrap">
                                    <thead>
                                        <tr>
                                            <th
                                                class="px-4 py-3 title-font tracking-wider font-medium text-gray-900 text-sm bg-gray-100 rounded-tl rounded-bl"
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
                                        <tr v-for="note in props.notes" :key="note.id">
                                            <td class="px-4 py-3">
                                                <Link :href="route('notes.show', { note: note })">
                                                    {{ note.id }}
                                                </Link>
                                            </td>
                                            <td class="px-4 py-3">{{ note.title }}</td>
                                            <td class="px-4 py-3">{{ note.url }}</td>
                                            <td class="px-4 py-3">{{ note.note }}</td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                        </div>
                    </section>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
