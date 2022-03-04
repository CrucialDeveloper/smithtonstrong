<template>
    <Head title="Is Walton's Open?" />

    <div class="w-screen h-screen flex items-center justify-center flex-col">
        <div class="text-5xl">Is Walton's Open?</div>

        <div class="mt-16 text-center" v-if="!open">
            <p class="text-9xl">NO!</p>
            <p class="text-3xl">I feel so sad!</p>
        </div>

        <div class="mt-16 text-center" v-if="open">
            <p class="text-9xl">YES!</p>
            <p class="text-3xl">What are you doing here? Go get ice cream!</p>
        </div>

        <vue-countdown
            class="mt-16 text-5xl"
            :time="countDownDate"
            v-slot="{ days, hours, minutes, seconds }"
        >Time Remaining：{{ days }} days, {{ hours }} hours, {{ minutes }} minutes, {{ seconds }} seconds.</vue-countdown>
    </div>
</template>



<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3';
import { ref, onMounted } from 'vue'
import VueCountdown from '@chenfengyuan/vue-countdown';

let openingDay = Date.parse('05 March 2022 11:00:00 -0600')
let countDownDate = openingDay - Date.now()

let open = openingDay - Date.now() < 0
console.log(open)




</script>