<template>
    <div class="bg-white border rounded py-4 px-8 mb-5">
        <div class="mb-4 text-xl font-medium line-through">{{ todo.text }}</div>
        <div class="flex justify-between items-center">
            <div class="text-gray-600">
                {{ new Date(todo.created_at).toLocaleTimeString() }}
            </div>
            <div>
                <a
                    class="text-red-500 hover:underline cursor-pointer"
                    v-on:click="removeTodo"
                    >Remove</a
                >
                <a
                    class="text-blue-500 ml-4 hover:underline cursor-pointer"
                    v-on:click="markAsDone"
                    >Mark as done</a
                >
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Todo",
    emits: ["remove-todo", "mark-as-done"],
    props: {
        todo: Object,
        i: Number,
    },

    methods: {
        removeTodo() {
            this.$emit("remove-todo", this.i);
        },

        markAsDone() {
            this.$emit("mark-as-done", this.i);
        },
    },
};
</script>

<style scoped></style>
