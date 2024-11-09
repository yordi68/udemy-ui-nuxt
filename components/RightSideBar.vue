<script>
export default {
    name: 'RightSideBar',
    data() {
        return {
            activeTab: 'personal',
            sticky: false, // new data property to control sticky behavior
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
            const offset = 250; // You can adjust this offset as needed
            this.sticky = window.scrollY > offset;
        },
    },
};
</script>


<template>
    <div 
    :class="[
            'bg-white  border border-white  w-[320px] shadow-lg transition-transform duration-300 mb-8',
            sticky ? 'sticky top-8 left-[62%]' : 'absolute top-36 right-96'
        ]"
    >
        <div class="flex flex-col">


            <div  :class="[sticky ? 'hidden' : 'relative h-48']">
                <div class="absolute inset-0 bg-black bg-opacity-50"></div>
                <img src="/assets/images/sidebar.jpg" alt="Course Preview Background" class="object-cover w-full h-full rounded-lg" />
                <div class="flex flex-col items-center justify-center absolute inset-0">
                    <button
                        class="bg-white text-black font-bold mb-4 rounded-full  shadow-md hover:bg-gray-300 transition-colors duration-300">
                        <div class="flex items-center">
                            <svg class="w-14 h-14" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M16 12L10 16V8L16 12Z" fill="currentColor"></path>
                            </svg>
                        </div>
                    </button>
                </div>
                <button
                    class="w-full absolute bottom-0 flex items-center justify-center py-2 z-10 bg-black bg-opacity-30">
                    <span class="text-white text-center font-medium ">Preview this course</span>
                </button>
            </div>

            <div class="flex mb-2 border-b">
                <button
                    class="bg-transparent text-gray-500 font-bold py-2 px-4 flex-1 hover:bg-white hover:text-black hover:border-b-2 hover:border-black"
                    :class="{ 'bg-white text-black border-b-2 border-black': activeTab === 'personal' }"
                    @click="activeTab = 'personal'">
                    Personal
                </button>
                <button
                    class="bg-transparent text-gray-500 font-bold py-2 px-4 flex-1 hover:bg-white hover:text-black hover:border-b-2 hover:border-black"
                    :class="{ 'bg-white text-black border-b-2 border-black': activeTab === 'teams' }"
                    @click="activeTab = 'teams'">
                    Teams
                </button>
            </div>


            <div v-if="activeTab === 'personal'" class="text-black p-4">
                <h3 class="text-xl font-semibold mb-2">Subscribe to Udemy's top courses</h3>
                <p class="text-sm mb-4">Get this course, plus 12,000+ of our top-rated courses, with Personal Plan.
                    <span class="underline  cursor-pointer text-purple-600 font-semibold">
                        Learn more
                    </span>
                </p>
                <button class="w-full text-center p-3 bg-purple-600 hover:bg-purple-700 text-white font-bold">
                    Try Personal Plan for free
                </button>
                <p class="text-sm mt-4 font-light px-8 text-center  text-gray-700">
                    Starting at $10.00 per month after trial.
                    Cancel anytime
                </p>

                <div class="my-4 flex flex-col">
                    <div class="flex items-center gap-2 text-gray-500">
                        <span class="text-xl font-bold text-gray-700">$13.99</span>
                        <span class="line-through ">$84.99</span>
                        <span class="text-black">84% off</span>
                    </div>
                    <p class="text-red-500 text-sm"><span class="font-bold">10 hours</span> left at this price!</p>
                    <button class="border border-black text-black w-full mt-3 py-3 font-bold hover:bg-slate-200">Add to
                        cart</button>
                </div>

                <p class="text-sm mt-4 font-light px-8 text-center text-gray-700">
                    0-Day Money-Back Guarantee
                    Full Lifetime Access
                </p>

                <div class="flex justify-between px-3ssss my-4">
                    <a href="#" class="text-black hover:text-gray-700 text-sm font-semibold underline">Share</a>
                    <a href="#" class="text-black hover:text-gray-700 text-sm font-semibold underline">Gift this
                        course</a>
                    <a href="#" class="text-black hover:text-gray-700 text-sm font-semibold underline">Apply Coupon</a>
                </div>

                <div class="w-full border border-dashed py-2 pl-4 text-gray-500 text-sm mb-2 pr-16">
                    <span class="font-bold">ST2MT110724BNEW</span> is applied Udemy coupon
                </div>

                <div class="flex items-center">
                    <input type="text" class="border border-black focus:outline-none flex-1  py-2 px-4 w-full"
                        placeholder="Enter Coupon" />
                    <button
                        class="bg-gray-700 border border-gray-700 hover:bg-gray-800 text-white py-2 px-4 ">Apply</button>
                </div>


            </div>

            <div v-if="activeTab === 'teams'" class="p-4 text-black">
                <h3 class="text-xl font-semibold mb-2">Udemy <span class="text-purple-600">business</span></h3>
                <p class="text-sm mb-4 pr-6">Subscribe to this course and 27,000+ top‑rated Udemy courses for your
                    organization.
                </p>
                <button class="w-full text-center p-3 bg-purple-600 hover:bg-purple-700 text-white font-bold">
                    Try Udemy Business
                </button>

                <div class="mt-8 text-gray-700 flex flex-col gap-4">
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