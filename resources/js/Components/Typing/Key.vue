<script setup>
import { defineProps } from "vue";

let props = defineProps({
    keyVal: {
        type: String,
        required: true,
    },
    keyCode: {
        type: String,
        required: true,
    },
    activeKey: {
        type: String,
        required: true,
    },
    width: {
        type: String,
        required: false,
        default: "w-16",
    },
});
</script>

<template>
    <div
        class="m-1 flex h-16 cursor-default select-none items-center justify-center rounded border border-gray-100 text-white"
        v-text="keyVal"
        :class="[
            {
                active: activeKey === keyCode,
            },
            width,
        ]"
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
