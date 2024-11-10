<script>
export default {
    name: 'RightSideBar',
    data() {
        return {
            activeTab: 'personal',
            sticky: false,
        };
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    beforeDestroy() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        handleScroll() {
            const offset = 250;
            this.sticky = window.scrollY > offset;
        },
    },
};
</script>


<template>
    <div :class="[
        'bg-white  border border-white  w-[320px] shadow-lg transition-transform duration-300 mb-8',
        sticky ? 'sticky top-8 left-[62%]' : 'absolute top-36 right-96'
    ]">
        <div class="flex flex-col">


            <div :class="[sticky ? 'hidden' : 'relative h-48']">
                <div class="absolute inset-0 bg-black bg-opacity-50"></div>
                <img src="/assets/images/sidebar.jpg" alt="Course Preview Background"
                    class="object-cover w-full h-full rounded-lg" />
                <div class="absolute inset-0 flex flex-col items-center justify-center">
                    <button
                        class="mb-4 font-bold text-black transition-colors duration-300 bg-white rounded-full shadow-md hover:bg-gray-300">
                        <div class="flex items-center">
                            <svg class="w-14 h-14" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M16 12L10 16V8L16 12Z" fill="currentColor"></path>
                            </svg>
                        </div>
                    </button>
                </div>
                <button
                    class="absolute bottom-0 z-10 flex items-center justify-center w-full py-2 bg-black bg-opacity-30">
                    <span class="font-medium text-center text-white ">Preview this course</span>
                </button>
            </div>

            <div class="flex mb-2 border-b">
                <button
                    class="flex-1 px-4 py-2 font-bold text-gray-500 bg-transparent hover:bg-white hover:text-black hover:border-b-2 hover:border-black"
                    :class="{ 'bg-white text-black border-b-2 border-black': activeTab === 'personal' }"
                    @click="activeTab = 'personal'">
                    Personal
                </button>
                <button
                    class="flex-1 px-4 py-2 font-bold text-gray-500 bg-transparent hover:bg-white hover:text-black hover:border-b-2 hover:border-black"
                    :class="{ 'bg-white text-black border-b-2 border-black': activeTab === 'teams' }"
                    @click="activeTab = 'teams'">
                    Teams
                </button>
            </div>


            <div v-if="activeTab === 'personal'" class="p-4 text-black">
                <h3 class="mb-2 text-xl font-semibold">Subscribe to Udemy's top courses</h3>
                <p class="mb-4 text-sm">Get this course, plus 12,000+ of our top-rated courses, with Personal Plan.
                    <span class="font-semibold text-purple-600 underline cursor-pointer">
                        Learn more
                    </span>
                </p>
                <button class="w-full p-3 font-bold text-center text-white bg-purple-600 hover:bg-purple-700">
                    Try Personal Plan for free
                </button>
                <p class="px-8 mt-4 text-sm font-light text-center text-gray-700">
                    Starting at $10.00 per month after trial.
                    Cancel anytime
                </p>

                <div class="flex flex-col my-4">
                    <div class="flex items-center gap-2 text-gray-500">
                        <span class="text-xl font-bold text-gray-700">$13.99</span>
                        <span class="line-through ">$84.99</span>
                        <span class="text-black">84% off</span>
                    </div>
                    <p class="text-sm text-red-500"><span class="font-bold">10 hours</span> left at this price!</p>
                    <button class="w-full py-3 mt-3 font-bold text-black border border-black hover:bg-slate-200">Add to
                        cart</button>
                </div>

                <p class="px-8 mt-4 text-sm font-light text-center text-gray-700">
                    0-Day Money-Back Guarantee
                    Full Lifetime Access
                </p>

                <div class="flex justify-between my-4 px-3ssss">
                    <a href="#" class="text-sm font-semibold text-black underline hover:text-gray-700">Share</a>
                    <a href="#" class="text-sm font-semibold text-black underline hover:text-gray-700">Gift this
                        course</a>
                    <a href="#" class="text-sm font-semibold text-black underline hover:text-gray-700">Apply Coupon</a>
                </div>

                <div class="w-full py-2 pl-4 pr-16 mb-2 text-sm text-gray-500 border border-dashed">
                    <span class="font-bold">ST2MT110724BNEW</span> is applied Udemy coupon
                </div>

                <div class="flex items-center">
                    <input type="text" class="flex-1 w-full px-4 py-2 border border-black focus:outline-none"
                        placeholder="Enter Coupon" />
                    <button
                        class="px-4 py-2 text-white bg-gray-700 border border-gray-700 hover:bg-gray-800 ">Apply</button>
                </div>


            </div>

            <div v-if="activeTab === 'teams'" class="p-4 text-black">
                <h3 class="mb-2 text-xl font-semibold">Udemy <span class="text-purple-600">business</span></h3>
                <p class="pr-6 mb-4 text-sm">Subscribe to this course and 27,000+ top‑rated Udemy courses for your
                    organization.
                </p>
                <button class="w-full p-3 font-bold text-center text-white bg-purple-600 hover:bg-purple-700">
                    Try Udemy Business
                </button>

                <div class="flex flex-col gap-4 mt-8 text-gray-700">
                    <div class="flex items-center ">
                        <svg class="w-4 h-4 mr-2 " viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M20 6L9 17L4 12" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                stroke-linejoin="round" />
                        </svg>
                        <span class="text-sm">For teams of 2 or more users</span>
                    </div>
                    <div class="flex items-center ">
                        <svg class="w-4 h-4 mr-2 " viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M20 6L9 17L4 12" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                stroke-linejoin="round" />
                        </svg>
                        <span class="text-sm">27,000+ fresh & in-demand courses</span>
                    </div>
                    <div class="flex items-center ">
                        <svg class="w-4 h-4 mr-2 " viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M20 6L9 17L4 12" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                stroke-linejoin="round" />
                        </svg>
                        <span class="text-sm">Learning Engagement tools</span>
                    </div>
                    <div class="flex items-center ">
                        <svg class="w-4 h-4 mr-2 " viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M20 6L9 17L4 12" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                stroke-linejoin="round" />
                        </svg>
                        <span class="text-sm">SSO and LMS Integrations</span>
                    </div>
                </div>

            </div>

        </div>
    </div>
</template>