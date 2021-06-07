<template>
    <div class="bg-white py-5 m-5 px-10 shadow-lg rounded">
        <h3 class="text-xl font-bold">Create A new Todo</h3>
        <input
            type="text"
            v-model="input"
            class="
                border
                w-full
                p-2
                px-4
                bg-gray-100
                focus:shadow-md focus:outline-none
                my-5
            "
        />
        <button
            @click="addTodo"
            class="
                my-2
                bg-purple-500
                text-white
                px-4
                py-2
                rounded
                shadow-md
                focus:shadow-lg focus:outline-none
            "
        >
            Add Todo
        </button>
    </div>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
    emits: ["add-todo"],
    setup(props, { emit }) {
        const input = ref("");

        const addTodo = () => {
            emit("add-todo", input.value);
            input.value = "";
        };

        return { input, addTodo };
    },
});
</script>

<style scoped></style>
