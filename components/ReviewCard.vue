<template>
    <div class="w-[60%] mx-auto  text-gray-800">
    <div class="w-[64%] space-y-8">
        
        <div class="grid grid-cols-2 gap-x-6">
            <div v-for="review in reviews" :key="review.id" class="max-w-xl py-4 border-t">
                <div class="flex flex-col items-start gap-4 ">
                    <div class="flex justify-between items-center gap-4 w-full">
                        <div class="flex items-center justify-center flex-shrink-0 w-10 h-10 bg-gray-900 rounded-full"
                        :class="{ 'bg-purple-700': review.id === 3 }">
                            <span class="font-medium text-white">{{ review.initials }}</span>
                         </div>
                         <div class="flex-1">
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
                    

                        
                        <div class="mt-2 text-gray-700 text-sm">
                            <p>
                                {{ review.text.slice(0, review.isExpanded ? undefined : 150) }}
                                {{ !review.isExpanded && review.text.length > 150 ? '...' : '' }}
                            </p>

                            <div v-if="review.text.length > 150" @click="toggleExpand(review.id)"
                                class="inline-flex items-center gap-1 mt-1 text-gray-600 cursor-pointer">
                                <span :class="{ 'font-bold': !review.isExpanded, 'font-bold': review.isExpanded }">
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
</template>

<script setup>
import { ref } from 'vue'
import { Star, MoreVertical, ChevronDown, ChevronUp, ThumbsUp, ThumbsDown } from 'lucide-vue-next'

const reviews = ref([
    {
        id: 1,
        name: 'Rommel S.',
        initials: 'RS',
        rating: 5,
        timeAgo: '4 months ago',
        text: '"User Experience (UX): The Ultimate Guide to Usability and UX" on Udemy is an outstanding course that provides a comprehensive introduction to UX design and usability. It is well-organized, covering everything from the basics of user research to advanced interaction design principles.',
        isExpanded: false
    },
    {
        id: 2,
        name: 'Eliza S.',
        initials: 'ES',
        rating: 5,
        timeAgo: '8 months ago',
        text: 'I find the overall experience inspiring and the course accomplishable. D. Travis is an excellent teacher, expert in the field. The lessons are full of theory and activities, allowing to build skill as well as understanding of the concepts.',
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
    },
    {
        id: 4,
        name: 'Markus G.',
        initials: 'MG',
        rating: 4,
        timeAgo: '9 months ago',
        text: 'All in all, a great course! The theoretical content was very interesting, entertaining and also very well structured. Only the tasks in the practical part are a bit outdated and need an update. I lost interest in the «Digital Prototyping» section.',
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