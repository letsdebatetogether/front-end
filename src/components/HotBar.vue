<script setup>
import { useDark, useToggle } from '@vueuse/core'
import {useRouter} from "vue-router";

const isDark = useDark()
const toggleDark = useToggle(isDark)

const router = useRouter()

const goTopic = () => {
    console.log("goTopic")
    router.push({name: "topic"})
}
</script>


<template>
    <header class="flex w-full bg-[#CFD1E1] dark:bg-[#343438]">
        <nav class="container flex w-full py-2 sm:flex-row">
            <div class="flex w-full pl-2 max-w-[12rem] md:pl-4 md:max-w-[18rem]">
                <p class="px-4 truncate ">Let's Debate Together</p>
                <button class="flex rounded-md bg-light_blue_button dark:bg-dark_blue_button" @click="goTopic()" > <p class="mx-1">TOPICS</p> </button>
            </div>

            <div class="hidden justify-center">{{ isDark }}</div>

            <div class="flex w-full items-center justify-end">
                <i class="fa-regular fa-user pr-4 text-xl"></i>
                <!-- TODO put  moon image / button -->
            </div>
        </nav>
        <div class="flex items-center justify-end">
            <button @click="toggleDark()">
                <i class="fa-regular fa-moon text-xl pr-3 dark:hidden"></i>
                <i class="hidden fa-regular fa-sun text-xl pr-3 dark:flex"></i>
            </button>
        </div>
    </header>
</template>


