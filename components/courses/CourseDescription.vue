<script>
export default {
    name: 'CourseDescription',
    data() {
        return {
            expanded: false
        }
    },
    methods: {
        toggleExpansion() {
            this.expanded = !this.expanded
        }
    }
}
</script>

<template>
    <div class="w-[60%] mx-auto mt-8 ">
        <div class="w-[67%] text-gray-700">
            <div class="">
                <h2 class="mb-4 font-sans text-3xl font-bold">Requirments</h2>
                <ul class="px-6 space-y-2">
                    <li class="list-disc">You don't need a background in user experience, design or coding to take this
                        course.</li>
                    <li class="list-disc">This is an in-depth course. If you allocate 60-90 mins a day, and do all of
                        the activities, it will take 2-3 weeks to complete.</li>
                </ul>
            </div>

            <div class="mt-8 ">
                <h2 class="mb-4 font-sans text-3xl font-bold">Description</h2>
                <div class="text-gray-700">
                    <h3 class="text-lg font-bold">2023 Edition.</h3>
                    <p class="mt-2">
                        You've just landed on Udemy's highest rated course on user experience (UX). Thousands of user
                        researchers and designers have used this course to kick-start their career in UX. You can do it,
                        too.
                    </p>
                    <div class="mt-4">
                        <h3 class="text-lg font-bold">Gain hands-on practice in all the key areas of UX</h3>
                        <p class="mt-2">— from interviewing your users through to prototyping and usability testing your
                            designs.</p>
                    </div>
                    <div class="mt-4">
                        <h3 class="text-lg font-bold">Build a UX portfolio to boost your job prospects</h3>
                        <p class="mt-2">as you complete five real-world sample projects.</p>
                    </div>
                    <div class="mt-4">
                        <h3 class="text-lg font-bold">Gain industry-recognised certification</h3>
                        <p class="mt-2">by preparing for the BCS Foundation Certificate in User Experience.</p>
                    </div>
                    <div class="mt-4">
                        <p>
                            UX Mastery reviewed dozens of online courses in UX, but they gave just one course 10/10:
                            <span class="font-bold">this one.</span>
                        </p>
                    </div>

                    <div v-if="expanded">
                        <div class="mt-4">
                            <h3 class="text-lg font-bold">Build Your UX Portfolio As You Work Through 5 User Research
                                and
                                Design Projects.</h3>
                            <p class="mt-2">The sample projects in the course include:</p>
                            <ul class="pl-6 mt-2 list-disc">
                                <li>Find my pet: a product that allows people to track down wayward pets who have got
                                    lost.
                                </li>
                                <li>Tomorrow's shopping cart: a device that lets customers find any product in a
                                    supermarket.</li>
                                <li>Gift Giver, a gift recommendation system based on an extremely accurate product
                                    recommendation technology.</li>
                                <li>The Citizen Journalist: a system that will allow ordinary people to film events,
                                    take
                                    photographs, write a story and create a crowdsourced, online newspaper.</li>
                                <li>The Digital Postcard, an app that will allow users to create and send their own
                                    postcard, either by using a photograph they have taken on their phone, or by
                                    selecting a
                                    professionally taken image of a local beauty spot.</li>
                            </ul>
                        </div>
                        <div class="mt-4">
                            <p>
                                A career in User Experience is one of the most rewarding and challenging jobs in the
                                technology sector. This online training course will give you the background you need to
                                get
                                started.
                            </p>
                        </div>
                        <div class="mt-4">
                            <h3 class="text-lg font-bold">Prepare for the BCS Foundation Certificate in User Experience.
                            </h3>
                            <p class="mt-2">
                                This course covers the comprehensive syllabus for the BCS Foundation Certificate in User
                                Experience and contains 90 multiple-choice quiz questions to test your knowledge and
                                prepare
                                for the exam. You can take the exam (at extra cost) anywhere in the world at a Pearson
                                Vue
                                exam centre.
                            </p>
                        </div>
                        <div class="mt-4">
                            <h3 class="text-lg font-bold">Free bonus offer!</h3>
                            <p class="mt-2">
                                Free 14-day extended access to dozens of UX methods, techniques and UX portfolio
                                templates
                                to support your learning.
                            </p>
                        </div>
                    </div>
                    <div class="flex justify-start mt-4">
                        <button @click="toggleExpansion" class="font-bold text-purple-600 hover:underline">
                            {{ expanded ? 'Show less' : 'Show more' }}
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
