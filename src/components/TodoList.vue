<template>
    <div>
        <ul>
            <TodoItem v-for:="(todo, i) in todos"
            v-bind:todo="todo"  v-bind:index="i" v-on:remove-todo="removeTodo"
            />
        </ul>
    </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue'
export default {
    props: ['todos'],
    components: {
        TodoItem
    },
    methods: {
        removeTodo() {
            this.$emit('remove-todo', id)
        }
    }
}
</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>