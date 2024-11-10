<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { StarIcon, SearchIcon, ShoppingCartIcon, GlobeIcon, XIcon } from 'lucide-vue-next'

const isScrolled = ref(false)
const showPurpleBanner = ref(true)
const remainingTime = ref('')

const calculateRemainingTime = (endTime) => {
    const now = new Date().getTime()
    const timeLeft = endTime - now

    if (timeLeft <= 0) {
        showPurpleBanner.value = false
        return ''
    }

    const hours = Math.floor(timeLeft / (1000 * 60 * 60))
    const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60))
    const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000)

    return `${hours}h ${minutes}m ${seconds}s`
}

onMounted(() => {
    window.addEventListener('scroll', () => {
        isScrolled.value = window.scrollY > 100
    })

    const endTime = new Date().getTime() + 24 * 60 * 60 * 1000

    const intervalId = setInterval(() => {
        remainingTime.value = calculateRemainingTime(endTime)
        if (!showPurpleBanner.value) clearInterval(intervalId)
    }, 1000)

    remainingTime.value = calculateRemainingTime(endTime)
})

onUnmounted(() => {
    window.removeEventListener('scroll', () => {
        isScrolled.value = window.scrollY > 100
    })
})
</script>

<template>
    <div class="z-50">
        <div v-show="showPurpleBanner && !isScrolled"
            class="bg-[#5624d0] text-white px-4 py-2 flex justify-between items-center text-sm">
            <div class="flex-1"></div>
            <div class="flex-grow text-center">
                <span class="font-bold">Ready to get with the times?</span>
                <span class="mx-2">|</span>
                <span>Get the skills with Udemy Business.</span>
                <span v-if="remainingTime" class="ml-2">({{ remainingTime }} left)</span>
            </div>
            <div class="flex justify-end flex-1">
                <button @click="showPurpleBanner = false" class="hover:text-gray-200">
                    <XIcon class="w-5 h-5" />
                </button>
            </div>
        </div>

        <div v-show="!isScrolled" class="px-4 py-2 bg-white border-b border-gray-200">
            <div class="flex items-center gap-4 px-12 mx-auto">
                <a href="#" class="text-lg font-semibold text-black">Udemy</a>

                <button class="text-sm font-medium text-gray-700 hover:text-gray-900">
                    Categories
                </button>

                <div class="relative flex-1">
                    <div class="absolute inset-y-0 flex items-center left-3">
                        <SearchIcon class="w-5 h-5 text-gray-400" />
                    </div>
                    <input type="text" placeholder="Search for anything"
                        class="w-full py-2 pl-10 pr-4 text-sm border border-gray-900 rounded-full focus:outline-none focus:border-purple-600" />
                </div>

                <nav class="flex items-center gap-4">
                    <a href="#" class="text-sm text-gray-700 hover:text-gray-900 whitespace-nowrap">
                        Udemy Business
                    </a>
                    <a href="#" class="text-sm text-gray-700 hover:text-gray-900 whitespace-nowrap">
                        Teach on Udemy
                    </a>
                    <button class="text-gray-700 hover:text-gray-900">
                        <ShoppingCartIcon class="w-6 h-6" />
                    </button>
                </nav>

                <div class="flex items-center gap-2">
                    <button class="px-4 py-2 text-sm font-bold text-gray-700 hover:text-gray-900">
                        Log in
                    </button>
                    <button class="px-4 py-2 text-sm font-bold text-white bg-black rounded hover:bg-gray-900">
                        Sign up
                    </button>
                    <button class="p-2 text-gray-700 border border-gray-700 rounded hover:text-gray-900">
                        <GlobeIcon class="w-5 h-5" />
                    </button>
                </div>
            </div>
        </div>

        <div v-show="isScrolled" class="fixed top-0 w-full px-4 py-4 text-white bg-black ">
            <div class="px-12 mx-auto bg-black">
                <h1 class="text-lg">
                    User Experience (UX): The Ultimate Guide to Usability and UX
                </h1>
                <div class="flex items-center gap-2 text-sm">
                    <div class="flex items-center">
                        <span class="text-[#e59819] font-bold">4.6</span>
                        <StarIcon class="w-4 h-4 text-[#e59819] ml-1" />
                    </div>
                    <span class="text-[#cec0fc]">(6,626 ratings)</span>
                    <span class="text-white">23,175 students</span>
                </div>
            </div>
        </div>
    </div>
</template>
