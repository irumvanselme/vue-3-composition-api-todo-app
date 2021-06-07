<template>
    <div class="bg-purple-500 px-12 flex">
        <router-link to="/">
            <div :class="linkClass">Home</div>
        </router-link>

        <router-link to="/todos">
            <div :class="linkClass">Todos</div>
        </router-link>
    </div>
</template>
<script>
export default {
    data: () => ({
        linkClass:
            "p-3 px-5 text-white hover:bg-white hover:text-purple-500 cursor-pointer transition-colors",
    }),
};
</script>
