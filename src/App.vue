<template>
    <div class="bg-gray-100 _container">
        <Navbar />
        <div class="container mx-auto mt-5">
            <router-view />
        </div>
    </div>
</template>
<script>
import Navbar from "./components/Navbar";

export default {
    components: { Navbar },
};
</script>

<style lang="scss">
._container {
    min-height: 100vh;
}
</style>
