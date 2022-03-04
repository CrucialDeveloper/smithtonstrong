<template>
    <Head title="Is Walton's Open?" />

    <div class="flex flex-col items-center justify-center mx-auto">
        <div class="text-5xl text-center">Is Walton's Open?</div>

        <div class="mt-16 text-center" v-if="!open">
            <p class="text-9xl">NO!</p>
            <p class="text-3xl">I feel so sad!</p>
            <img src="https://media.giphy.com/media/9Y5BbDSkSTiY8/giphy.gif" alt />
        </div>

        <div class="mt-16 text-center" v-if="open">
            <p class="text-9xl">YES!</p>
            <p class="text-3xl">What are you doing here? Go get ice cream!</p>
            <img src="https://media.giphy.com/media/26uf7yJapo82e48yA/giphy.gif" alt />
        </div>

        <vue-countdown
            v-if="!open"
            class="mt-16 text-5xl"
            :time="countDownDate"
            v-slot="{ days, hours, minutes, seconds }"
        >Time Remaining：{{ days }} days, {{ hours }} hours, {{ minutes }} minutes, {{ seconds }} seconds.</vue-countdown>

        <p class="mt-8 text-3xl">
            <a
                class="text-blue-500 underline hover:text-blue-600"
                href="https://www.facebook.com/WaltonsIceCream"
            >Walton's Ice Cream</a>
        </p>
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