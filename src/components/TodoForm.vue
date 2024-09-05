<template>
    <div>
        <form @submit.prevent="addItemToCart(todo)">
            <input v-model="todo" type="text" />
            <button>Add</button>
        </form>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import { useTodoListStore } from '@/stores/todoList';
const todo = ref('')

const store = useTodoListStore()

function addItemToCart(item) {
    if(item.length === 0) {
        return 
    } 
    store.addTodo(item)
    todo.value = ''
}
</script>

<style lang="scss" scoped>

</style>