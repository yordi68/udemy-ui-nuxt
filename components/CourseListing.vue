<template>
    <div class="w-[60%] mx-auto">
    <div class="w-[64%] py-8 ">
        <h2 class="mb-6 text-2xl font-bold">
            More Courses by <a href="#" class="text-purple-600 hover:underline">David Travis</a>
        </h2>

        <div class="grid grid-cols-1 gap-3 md:grid-cols-2 lg:grid-cols-3">
            
            <div v-for="course in courses" :key="course.id" class="overflow-hidden bg-white ">
                <a href="#" class="block">
                    <img :src="course.image" :alt="course.imageAlt" class="object-cover w-full h-32">
                    <div class="py-4">
                        <h3 class="mb-1 text-lg font-semibold">{{ course.title }}</h3>
                        <p class="mb-2 text-sm text-gray-600">{{ course.instructor }}</p>

                        
                        <div class="flex items-center gap-1 mb-2">
                            <span class="font-semibold">{{ course.rating }}</span>
                            <div class="flex text-yellow-400">
                                <svg v-for="i in 5" :key="i" :class="{
                                    'text-yellow-400': i <= Math.floor(course.rating),
                                    'text-gray-300': i > Math.ceil(course.rating)
                                }" class="w-4 h-4" viewBox="0 0 24 24" fill="currentColor">
                                    <path
                                        d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z" />
                                </svg>
                            </div>
                            <span class="text-sm text-gray-600">({{ course.reviews }})</span>
                        </div>

                        
                        <p class="mb-2 text-sm text-gray-600">
                            {{ course.hours }} total hours · {{ course.lectures }} lectures · {{ course.level }}
                        </p>

                        
                        <p class="font-semibold">{{ course.price === 0 ? 'Free' : `$${course.price.toFixed(2)}` }}</p>
                    </div>
                </a>
            </div>
        </div>

        <button class="border border-black text-black w-full mt-3 py-2.5 text-sm font-bold hover:bg-slate-200">2
                Report Abuse
        </button>
    </div>
</div>
</template>

<script setup>
const courses = [
    {
        id: 1,
        title: 'Usability Testing Boot Camp',
        instructor: 'David Travis',
        rating: 4.6,
        reviews: 842,
        hours: 8.5,
        lectures: 48,
        level: 'Beginner',
        price: 19.99,
        image: '/assets/images/course-1.jpg',
        imageAlt: 'Student studying at computer'
    },
    {
        id: 2,
        title: 'How to carry out a usability expert review',
        instructor: 'David Travis',
        rating: 4.5,
        reviews: 638,
        hours: 5.5,
        lectures: 38,
        level: 'Intermediate',
        price: 19.99,
        image: '/assets/images/course-2.jpg',
        imageAlt: 'Person filling out checklist'
    },
    {
        id: 3,
        title: 'User Experience Certification',
        instructor: 'David Travis',
        rating: 4.3,
        reviews: 2734,
        hours: 1,
        lectures: 17,
        level: 'Intermediate',
        price: 0,
        image: '/assets/images/sidebar.jpg',
        imageAlt: 'Diploma with red ribbon'
    }
]
</script>
