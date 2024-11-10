<script setup>
import { ref } from 'vue'
import { Dialog, DialogPanel } from '@headlessui/vue'
import { Star, Search, X, MoreVertical, ChevronDown, ChevronUp, ThumbsUp, ThumbsDown } from 'lucide-vue-next'

const isOpen = ref(false)
const openModal = () => {
    isOpen.value = true
}
const closeModal = () => {
    isOpen.value = false
}

const ratings = [
    { stars: 5, percentage: 61 },
    { stars: 4, percentage: 30 },
    { stars: 3, percentage: 8 },
    { stars: 2, percentage: 1 },
    { stars: 1, percentage: 0 }
]

const reviews = ref([
    {
        id: 1,
        name: 'Rommel S.',
        initials: 'RS',
        rating: 5,
        timeAgo: '4 months ago',
        text: '"User Experience (UX): The Ultimate Guide to Usability and UX" on Udemy is an outstanding course that provides a comprehensive introduction to UX design and usability. It is well-organized, covering everything from the basics of UX design to advanced usability testing, ensuring a smooth learning curve for beginners and valuable insights for experienced professionals. The course includes practical examples and real-world case studies, making complex concepts easy to understand and apply. Emphasizing a user-centered approach, it teaches learners to design with the user in mind, which is crucial for creating effective and engaging digital experiences.',
        isExpanded: false
    },
    {
        id: 2,
        name: 'Eliza S.',
        initials: 'ES',
        rating: 5,
        timeAgo: '8 months ago',
        text: 'I find the overall experience inspiring and the course accomplishable. D. Travis is an excellent teacher, expert in the field. The lessons are full of theory and activities, allowing to build skill as well as understanding. He tackles difficult topics with ease and fun. There are quite many resources suggested for further learning as well. What I find important, is that the course is kept updated and I have a "busy" feeling around it as there are many Q&A under each lesson and a couple of ways how to contact the teacher.',
        isExpanded: false
    },
    {
        id: 3,
        name: '허인국',
        initials: '허',
        rating: 5,
        timeAgo: '9 months ago',
        text: 'He takes us many quize and knowhow which helps us to reach end of course. He is good teacher for us.',
        isExpanded: false
    }
])

const toggleExpand = (id) => {
    const review = reviews.value.find(r => r.id === id)
    if (review) {
        review.isExpanded = !review.isExpanded
    }
}
</script>

<template>
    <div class="w-[60%] mx-auto">

        <button @click="openModal" class="px-6 py-2 text-sm font-medium border border-gray-800 hover:bg-gray-50">
            Show all reviews
        </button>

        <Dialog :open="isOpen" @close="closeModal" class="relative z-50">
            <div class="fixed inset-0 bg-black/30" aria-hidden="true" />

            <div class="fixed inset-0 overflow-y-auto">
                <div class="flex items-start justify-center min-h-full p-4">
                    <DialogPanel class="w-full max-w-4xl p-6 mt-8 bg-white rounded-lg">

                        <div class="flex items-center justify-between mb-6">
                            <div class="flex items-center gap-3">
                                <Star class="w-6 h-6 text-yellow-400 fill-current" />
                                <span class="text-xl font-bold">4.6 course rating</span>
                                <span class="text-xl">•</span>
                                <span class="text-xl">7K ratings</span>
                            </div>
                            <button @click="closeModal" class="text-gray-400 hover:text-gray-500">
                                <X class="w-6 h-6" />
                            </button>
                        </div>

                        <div class="flex gap-8">

                            <div class="w-64 space-y-4">
                                <div v-for="(rating, index) in ratings" :key="index" class="flex items-center gap-2">
                                    <div class="flex items-center w-24 gap-1">
                                        <Star v-for="star in 5" :key="star" :class="[
                                            'w-4 h-4',
                                            star <= 5 - index ? 'text-yellow-400 fill-current' : 'text-gray-300 fill-current'
                                        ]" />
                                    </div>
                                    <div class="flex-1 h-2 overflow-hidden bg-gray-200 rounded-full">
                                        <div class="h-full bg-gray-700 rounded-full"
                                            :style="{ width: `${rating.percentage}%` }" />
                                    </div>
                                    <span class="w-12 text-sm text-gray-600">{{ rating.percentage }}%</span>
                                </div>


                                <div class="relative">
                                    <input type="text" placeholder="Search reviews"
                                        class="w-full py-2 pl-8 pr-4 border rounded-md" />
                                    <Search class="absolute w-4 h-4 text-gray-400 -translate-y-1/2 left-2 top-1/2" />
                                </div>
                            </div>


                            <div class="flex-1 space-y-8">
                                <div v-for="review in reviews" :key="review.id" class="pb-6 border-b">
                                    <div class="flex items-start gap-4">
                                        <div class="flex items-center justify-center flex-shrink-0 w-10 h-10 bg-gray-900 rounded-full"
                                            :class="{ 'bg-purple-700': review.id === 3 }">
                                            <span class="font-medium text-white">{{ review.initials }}</span>
                                        </div>

                                        <div class="flex-1">
                                            <div class="flex items-center justify-between">
                                                <div>
                                                    <h3 class="font-medium">{{ review.name }}</h3>
                                                    <div class="flex items-center gap-2">
                                                        <div class="flex">
                                                            <Star v-for="i in 5" :key="i" :class="[
                                                                'w-4 h-4',
                                                                i <= review.rating ? 'text-yellow-400 fill-current' : 'text-gray-300 fill-current'
                                                            ]" />
                                                        </div>
                                                        <span class="text-sm text-gray-500">{{ review.timeAgo }}</span>
                                                    </div>
                                                </div>

                                                <button class="text-gray-500 hover:text-gray-700">
                                                    <MoreVertical class="w-5 h-5" />
                                                </button>
                                            </div>

                                            <div class="mt-2 text-gray-700">
                                                <p>
                                                    {{ review.isExpanded ? review.text : review.text.slice(0, 150) +
                                                        '...' }}
                                                </p>

                                                <div v-if="review.text.length > 150" @click="toggleExpand(review.id)"
                                                    class="inline-flex items-center gap-1 mt-1 text-gray-600 cursor-pointer">
                                                    <span
                                                        :class="{ 'font-bold': !review.isExpanded, 'font-normal': review.isExpanded }">
                                                        {{ review.isExpanded ? 'Show less' : 'Show more' }}
                                                    </span>
                                                    <ChevronDown v-if="!review.isExpanded" class="w-4 h-4" />
                                                    <ChevronUp v-if="review.isExpanded" class="w-4 h-4" />
                                                </div>
                                            </div>

                                            <div class="flex items-center gap-4 mt-4">
                                                <span class="text-sm text-gray-500">Helpful?</span>
                                                <button class="text-gray-500 hover:text-gray-700">
                                                    <ThumbsUp class="w-5 h-5" />
                                                </button>
                                                <button class="text-gray-500 hover:text-gray-700">
                                                    <ThumbsDown class="w-5 h-5" />
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </DialogPanel>
                </div>
            </div>
        </Dialog>
    </div>
</template>
