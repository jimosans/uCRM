<script setup>
import { Link } from "@inertiajs/inertia-vue3";
defineProps({
    blogs: Array
})
</script>
<template>
    <div v-if="$page.props.flash.message" class="bg-red-500 alert alert-success">
        {{ $page.props.flash.message }}
    </div>
    <ul>
        <li v-for="blog in blogs" :key="blog.id">
            <Link class="text-blue-500" :href="route('inertia.show', {id: blog.id})">件名:{{ blog.title }},本文:{{ blog.content }}</Link>
        </li>
    </ul>
あああああ
</template>