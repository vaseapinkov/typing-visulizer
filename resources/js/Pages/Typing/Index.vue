<script setup>
import { reactive, ref, watch } from "vue";

import { Head, Link } from "@inertiajs/inertia-vue3";

import Key from "@/Components/Typing/Key.vue";
import SpaceKey from "@/Components/Typing/SpaceKey.vue";

let lettersByLines = [
    {
        letters: [
            {
                value: "Tab",
                code: "Tab",
                width: "w-16",
            },
            {
                value: "q",
                code: "KeyQ",
            },
            {
                value: "w",
                code: "KeyW",
            },
            {
                value: "e",
                code: "KeyE",
            },
            {
                value: "r",
                code: "KeyR",
            },
            {
                value: "t",
                code: "KeyT",
            },
            {
                value: "y",
                code: "KeyY",
            },
            {
                value: "u",
                code: "KeyU",
            },
            {
                value: "i",
                code: "KeyI",
            },
            {
                value: "o",
                code: "KeyO",
            },
            {
                value: "p",
                code: "KeyP",
            },
            {
                value: "[",
                code: "BracketLeft",
            },
            {
                value: "]",
                code: "BracketRight",
            },
            {
                value: "\\",
                code: "Backslash",
            },
        ],
    },
    {
        letters: [
            {
                value: "Caps",
                code: "CapsLock",
                width: "w-20",
            },
            {
                value: "a",
                code: "KeyA",
            },
            {
                value: "s",
                code: "KeyS",
            },
            {
                value: "d",
                code: "KeyD",
            },
            {
                value: "f",
                code: "KeyF",
            },
            {
                value: "g",
                code: "KeyG",
            },
            {
                value: "h",
                code: "KeyH",
            },
            {
                value: "j",
                code: "KeyJ",
            },
            {
                value: "k",
                code: "KeyK",
            },
            {
                value: "l",
                code: "KeyL",
            },
            {
                value: ";",
                code: "Semicolon",
            },
            {
                value: "'",
                code: "Quote",
            },
            {
                value: "Enter",
                code: "Enter",
                width: "flex-1",
            },
        ],
    },
    {
        letters: [
            {
                value: "Shift",
                code: "ShiftLeft",
                width: "w-24",
            },
            {
                value: "z",
                code: "KeyZ",
            },
            {
                value: "x",
                code: "KeyX",
            },
            {
                value: "c",
                code: "KeyC",
            },
            {
                value: "v",
                code: "KeyV",
            },
            {
                value: "b",
                code: "KeyB",
            },
            {
                value: "n",
                code: "KeyN",
            },
            {
                value: "m",
                code: "KeyM",
            },
            {
                value: ",",
                code: "Comma",
            },
            {
                value: ".",
                code: "Period",
            },
            {
                value: "/",
                code: "Slash",
            },
            {
                value: "Shift",
                code: "ShiftRight",
                width: "flex-1",
            },
        ],
    },
    {
        letters: [
            {
                value: "Space",
                code: "Space",
                width: "flex-1",
            },
        ],
    },
];

let pressedKey = reactive({
    keyVal: "",
});

// Disable the default browser behavior of the keypress event
document.onkeydown = function (e) {
    return false;
};

window.addEventListener("keydown", (e) => {
    pressedKey.keyVal = e.code;
    let audio = new Audio("/audio/key-press-sound-3.mp3");
    audio.volume = 0.1;
    audio.play();
});
</script>

<template>
    <Head title="Typing App" />

    <div
        class="items-top relative flex min-h-screen justify-center bg-gray-100 dark:bg-gray-900 sm:items-center sm:pt-0"
    >
        <div class="flex flex-col">
            <div
                class="flex flex-row"
                v-for="(line, index) in lettersByLines"
                :key="index + '-line'"
            >
                <Key
                    v-for="(letter, index) in line.letters"
                    :key="index + '-letter'"
                    :keyVal="letter.value"
                    :keyCode="letter.code"
                    :width="letter.width"
                    :activeKey="pressedKey.keyVal"
                />
            </div>
        </div>
    </div>
</template>
