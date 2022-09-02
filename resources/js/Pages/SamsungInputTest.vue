<template>
    <div>
        <h1>Input 1</h1>
        <input type="file" accept="image/*,video/*" />

        <h1>Input 2</h1>
        <input type="file" accept="image/jpg,image/png,video/*" />

        <h1>Input 3</h1>
        <input type="file" accept="image/jpg,image/png,image/jpeg,video/*" />

        <h1>Input 4</h1>
        <input type="file" accept="image/*" />

        <h1>Input 5</h1>
        <input type="file" accept="image/jpg,image/png" />

        <h1>Input 6</h1>
        <input type="file" accept="image/jpg,image/png,image/jpeg" />

        <h1>Input 7</h1>
        <input type="file" accept="image/*" capture />

        <h1>Input 8</h1>
        <input type="file" accept="image/*" capture="user" />

        <h1>Input 9</h1>
        <input type="file" accept="image/*" capture="environment" />

        <h1>Input 10</h1>
        <input type="file" accept="image/jpg,image/png,video/*" />
    </div>
</template>

<script>
export default {
    name: "SamsungInputTest.vue",
};
</script>

<style scoped>
div {
    @apply ml-4;
}

h1 {
    @apply mt-4 text-xl font-semibold;
}
</style>
