<script setup>
import { Inertia } from '@inertiajs/inertia'

defineProps({
    id: String, // ここで型を指定する
    blog: Object
})

const deleteConfirm = id => {
    Inertia.delete(`/inertia/${id}`, {
        onBefore: () => confirm('削除しますか？')
    })
}
</script>

<template>
    <h1>id: {{ id }}</h1>
    {{ blog.title }}
    {{ blog.content }}
    <button @click="deleteConfirm(blog.id)">削除</button>
</template>

