<script setup>
import { defineProps } from "vue";

let props = defineProps({
    active: {
        type: Boolean,
        required: true,
    },
});
</script>

<template>
    <div
        class="m-1 flex h-10 items-center justify-center rounded border border-gray-100 text-white"
        :class="{ active }"
    ></div>
</template>

<style scoped>
div.active {
    animation-name: active;
    animation-duration: 0.5s;
}

@keyframes active {
    0% {
        @apply bg-gray-800;
    }
    50% {
        @apply bg-gray-600;
    }
    100% {
        @apply bg-gray-800;
    }
}
</style>
