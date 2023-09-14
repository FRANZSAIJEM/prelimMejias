<script setup>
import Layout from '@/Layouts/Layout.vue';
import { Head } from '@inertiajs/vue3';
</script>


<template>
    <Head title="Clients" />

    <Layout>
        <div class="">
            <div class="">
                <div class="">
                    <div class="p-6 text-gray-900">
                        <div v-for="client in clients.data" :key="client.id" style="display: inline-flex; flex-wrap: wrap;">
                            <div class="bg-green-900 text-white m-5 p-5 rounded-lg" style="width: 350px;">
                               <div class="rounded-2xl shadow-2xl mb-5" style="display: grid; place-content: center; background-color: rgb(46, 131, 46);">
                                <img width="170" src="https://static.vecteezy.com/system/resources/previews/022/665/468/non_2x/excited-3d-boy-jumping-on-white-transparent-background-free-png.png" alt="">
                               </div>
                                <b>Last Name: </b>{{ client.last_name }} <br>
                                <b>First Name: </b>{{ client.first_name }} <br>
                                <b>Address: </b>{{ client.address }} <br>
                                <b>Phone: </b>{{ client.phone }} <br>
                                <b>Level: </b>{{ client.level }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="mt-4 flex justify-between items-center">
    <div class="flex items-center space-x-2" style="transform: translateY(-20px) translateX(45px);">
        <span v-if="clients.prev_page_url">
            <a
                :href="clients.prev_page_url"
                @click.prevent="$inertia.visit(clients.prev_page_url)"
                class="text-sm font-medium text-gray-100 p-5 bg-green-900 rounded-md hover:bg-green-700 duration-100"
            >
                Previous
            </a>
        </span>

        <!-- Numbered Links Pagination -->
        <template v-if="clients.last_page > 1">
            <span v-for="page in clients.last_page" :key="page">
                <a
                    :href="'/clients?page=' + page"
                    @click.prevent="$inertia.visit('/clients?page=' + page)"
                    class="text-sm font-medium text-gray-100 p-5 bg-green-800 rounded-md hover:bg-green-700 duration-100"
                >
                    {{ page }}
                </a>
            </span>
        </template>

        <span v-if="clients.next_page_url">
            <a
                :href="clients.next_page_url"
                @click.prevent="$inertia.visit(clients.next_page_url)"
                class="text-sm font-medium text-gray-100 p-5 bg-green-900 rounded-md hover:bg-green-700 duration-100"
            >
                Next
            </a>
        </span>
    </div>
</div>

    </Layout>
</template>

<script>
export default {
    props: {
        clients: Object, // Define the clients prop type as an object
    },
};
</script>
