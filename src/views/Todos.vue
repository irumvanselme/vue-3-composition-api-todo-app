<template>
    <div class="about">
        <div class="grid grid-cols-2">
            <div>
                <h1 class="text-2xl font-black py-3">Your todos</h1>
                <hr />
                <div v-if="todos.length === 0">
                    <h3 class="text-center text-2xl my-8">No Tasks to do</h3>
                </div>
                <div v-for="(todo, index) in todos" :key="index">
                    <Todo
                        :todo="todo"
                        :i="index"
                        v-on:remove-todo="removeTodo"
                        v-on:mark-as-done="markAsDone"
                    />
                </div>
            </div>
            <div>
                <NewTodo v-on:add-todo="addTodo" />
            </div>
        </div>
    </div>
</template>
<script>
import { defineComponent, reactive } from "vue";

import NewTodo from "../components/NewTodo";
import Todo from "../components/todos/Todo";

export default defineComponent({
    components: { Todo, NewTodo },
    setup() {
        let todos = reactive([]);

        const addTodo = (value) => {
            todos.push({
                text: value,
                created_at: new Date(),
                done: false,
            });
        };

        const removeTodo = (index) => {
            todos.splice(index, 1);
        };

        const markAsDone = (index) => {
            todos[index].done = true;
        };

        return { todos, addTodo, removeTodo, markAsDone };
    },
});
</script>
