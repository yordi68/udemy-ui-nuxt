<script setup>
import { ref } from 'vue'
import { Star, Users, GraduationCap, PlayCircle, ChevronDown, ChevronUp } from 'lucide-vue-next'

const isExpanded = ref(false)
</script>

<template>
    <div class="w-[60%]  mx-auto">
        <div class="max-w-2xl p-4">
            <h2 class="mb-6 font-sans text-3xl font-bold">Instructor</h2>

            <a href="#" class="text-lg font-semibold text-purple-600 hover:underline">
                David Travis
            </a>

            <p class="mt-1 mb-4 text-gray-600">
                Author of 'Think Like a UX Researcher'
            </p>

            <div class="flex items-start gap-6 mb-6">
                <div class="flex-shrink-0">
                    <div class="w-[90px] h-[90px] rounded-full overflow-hidden">
                        <img src="/assets/images/person.jpeg" alt="Instructor profile"
                            class="object-cover w-full h-full" />
                    </div>
                </div>

                <div class="grid gap-1.5">
                    <div class="flex items-center gap-2">
                        <Star class="w-4 h-4 text-gray-600" />
                        <span class="text-sm text-gray-700">4.5 Instructor Rating</span>
                    </div>

                    <div class="flex items-center gap-2">
                        <Users class="w-4 h-4 text-gray-600" />
                        <span class="text-sm text-gray-700">10,931 Reviews</span>
                    </div>

                    <div class="flex items-center gap-2">
                        <GraduationCap class="w-4 h-4 text-gray-600" />
                        <span class="text-sm text-gray-700">69,157 Students</span>
                    </div>

                    <div class="flex items-center gap-2">
                        <PlayCircle class="w-4 h-4 text-gray-600" />
                        <span class="text-sm text-gray-700">5 Courses</span>
                    </div>
                </div>
            </div>

            <div class="space-y-4 text-sm leading-relaxed">
                <p>I'm on a mission to create more user experience professionals.</p>

                <p>
                    Perhaps you'd like a job in user experience. Or maybe you already work in the field but you've never
                    had
                    any formal
                    training. Or maybe you want to improve your skills in one specific area, like usability testing or
                    expert reviews.
                    <span v-if="isExpanded">
                        <strong>
                            I've turned thousands of people into user experience designers and researchers and now you
                            can
                            join their ranks by
                            taking my courses on Udemy.
                        </strong>
                    </span>
                </p>

                <template v-if="isExpanded">
                    <p>
                        You're probably curious about my background. At 18, I appeared as an extra in the film
                        "Quadrophenia" alongside
                        Sting and Ray Winstone. Despite a critically-acclaimed performance lasting 5 seconds, follow-up
                        offers from
                        Hollywood failed to arrive so I turned to psychology where I gained a BSc and a PhD. Since 1989
                        I've
                        worked in the
                        fields of human factors, usability and user experience and I've published three books on
                        usability,
                        including
                        "Think Like a UX Researcher". I'm now a User Experience Strategist at Userfocus, a consultancy
                        specializing in
                        user experience. I'm no longer in contact with Sting or Ray Winstone, whose career trajectories
                        have
                        been somewhat
                        different.
                    </p>

                    <p>
                        I've provided usability support to top brands like HP, Microsoft, Whirlpool, Orange, Skype, eBay
                        and
                        Yahoo! and
                        I've also consulted with public sector organisations like The Greater London Authority, Her
                        Majesty's Revenue and
                        Customs, UK Government and the World Health Organization.
                    </p>

                    <p>
                        My students describe me as passionate and technically knowledgeable and students voted me an
                        "Outstanding
                        Instructor" in a Udemy-wide survey.
                    </p>

                </template>
            </div>

            <div @click="isExpanded = !isExpanded" class="flex items-center gap-2 mt-4 text-purple-600 cursor-pointer">
                <span :class="{ 'font-bold': !isExpanded, 'font-bold': isExpanded }">
                    {{ isExpanded ? 'Show less' : 'Show more' }}
                </span>
                <ChevronDown v-if="!isExpanded" class="w-4 h-4" />
                <ChevronUp v-if="isExpanded" class="w-4 h-4" />
            </div>
        </div>

    </div>
</template>
