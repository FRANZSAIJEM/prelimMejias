<script setup>
import { Link } from '@inertiajs/vue3';
import { defineProps } from 'vue';

const {hidden} = defineProps (['hidden'])
</script>

<template>

    <div class="main-nav" style="text-align: start;">
        <Link :href="route('dashboard')" :active="route().current('dashboard')">
            <i style="width: 45px; margin-left: -13px; background-color: rgb(32, 106, 32); text-align: center; box-shadow: 0px 5px 5px 0px rgba(0, 0, 0, 0.159); padding: 10px; border-radius: 5px;" class="fa-solid fa-house-chimney"></i> <span :hidden="hidden">Dashboard</span>
        </Link>
        <Link :href="route('clients')" :active="route().current('clients')">
            <i style="width: 45px; margin-left: -13px; background-color: rgb(32, 106, 32); text-align: center; box-shadow: 0px 5px 5px 0px rgba(0, 0, 0, 0.159); padding: 10px; border-radius: 5px;" class="fa-solid fa-users"></i> <span :hidden="hidden">Clients</span>
        </Link>
        <Link :href="route('profile.edit')" :active="route().current('clients')">
            <i style="width: 45px; margin-left: -13px; background-color: rgb(32, 106, 32); text-align: center; box-shadow: 0px 5px 5px 0px rgba(0, 0, 0, 0.159); padding: 10px; border-radius: 5px;" class="fa-solid fa-user"></i> <span :hidden="hidden">Profile</span>
        </Link>
        <Link :href="route('logout')" method="post" >
            <i style="width: 45px; margin-left: -13px; background-color: rgb(32, 106, 32); text-align: center; box-shadow: 0px 5px 5px 0px rgba(0, 0, 0, 0.159); padding: 10px; border-radius: 5px;" class="fa-solid fa-right-from-bracket"></i> <span :hidden="hidden">Logout</span>
        </Link>

    </div>

</template>
