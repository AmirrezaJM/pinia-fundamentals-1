<template>
    <div v-for="todo in TodoList" :key="todo.id" class="item">
        {{ todo }}
        <div class="content">
            <span>{{ todo.item }}</span>
            <span @click.stop="toggleCompleted(todo.id)">&#10004;</span>
        </div>
    </div>
</template>

<script setup>
import { storeToRefs } from 'pinia'
import { useTodoListStore } from '../stores/todoList'

const store = useTodoListStore()
const { TodoList } = storeToRefs(store)
console.log(TodoList)
const { toggleCompleted } = store
</script>

<style lang="scss" scoped>

</style>