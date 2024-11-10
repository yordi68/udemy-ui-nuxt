<script>
export default {
    name: 'Recommendations',
    data() {
        return {
            courses: [
                {
                    id: 1,
                    title: 'UX & Web Design Master Course: Strategy, Design, Development',
                    image: '/assets/images/sidebar.jpg',
                    rating: 4,
                    numEnrollments: 106294,
                    price: 10.99,
                    description: '23 total hours · Updated 3/2020'
                },
                {
                    id: 2,
                    title: 'UX Strategy Fundamentals',
                    image: '/assets/images/course-1.jpg',
                    rating: 4.4,
                    numEnrollments: 25386,
                    price: 10.99,
                    description: '2.5 total hours · Updated 8/2016'
                },
                {
                    id: 3,
                    title: 'User Experience Design Fundamentals',
                    image: '/assets/images/course-2.jpg',
                    rating: 4.5,
                    numEnrollments: 111037,
                    price: 13.99,
                    description: '10 total hours · Updated 12/2019'
                },
                {
                    id: 4,
                    title: 'Object-Oriented UX (OOUX) Fundamentals',
                    image: '/assets/images/course-1.jpg',
                    rating: 4.6,
                    numEnrollments: 5981,
                    price: 10.99,
                    description: 'Highest Rated, 6.5 total hours · Updated 4/2023'
                },
                {
                    id: 5,
                    title: 'UX Design Process from User Research to Usability Testing',
                    image: '/assets/images/course-2.jpg',
                    rating: 4.2,
                    numEnrollments: 4172,
                    price: 10.99,
                    description: '5 total hours · Updated 1/2020'
                },
                {
                    id: 6,
                    title: 'Real World UX | Learn User Experience & Start Your Career',
                    image: '/assets/images/sidebar.jpg',
                    rating: 4.5,
                    numEnrollments: 15367,
                    price: 10.99,
                    description: '5.5 total hours · Updated 7/2023'
                }
            ]
        }
    }
}
</script>

<template>
    <div class="w-[60%] mx-auto py-6">
        <div class="w-[67%] text-gray-700">
            <h2 class="mb-6 font-sans text-3xl font-bold">Students also bought</h2>
            <div class="space-y-4 ">

                <div class="flex items-start justify-between py-2 border-b border-gray-300" v-for="course in courses"
                    :key="course.id">
                    <div class="flex items-start gap-4 w-[50%]">
                        <img :src="course.image" class="w-16 h-16 " :alt="course.title">

                        <div class="flex flex-col gap-1">
                            <h3 class="font-bold ">{{ course.title }}</h3>
                            <p class="text-sm">{{ course.description }}</p>
                        </div>
                    </div>

                    <div class="flex items-center gap-1">
                        <span class="text-yellow-700">{{ course.rating }}</span>
                        <svg class="w-5 h-5 text-yellow-500 fill-current">
                            <path
                                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                        </svg>
                    </div>
                    <div class="flex items-center gap-1 text-sm">
                        <svg class="w-4 h-4 text-gray-800" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                            width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
                            <path fill-rule="evenodd"
                                d="M8 4a4 4 0 1 0 0 8 4 4 0 0 0 0-8Zm-2 9a4 4 0 0 0-4 4v1a2 2 0 0 0 2 2h8a2 2 0 0 0 2-2v-1a4 4 0 0 0-4-4H6Zm7.25-2.095c.478-.86.75-1.85.75-2.905a5.973 5.973 0 0 0-.75-2.906 4 4 0 1 1 0 5.811ZM15.466 20c.34-.588.535-1.271.535-2v-1a5.978 5.978 0 0 0-1.528-4H18a4 4 0 0 1 4 4v1a2 2 0 0 1-2 2h-4.535Z"
                                clip-rule="evenodd" />
                        </svg>

                        <span>{{ course.numEnrollments }}</span>
                    </div>
                    <div>
                        <span class="text-sm font-bold text-gray-900">$"{{ course.price }}</span>
                    </div>
                    <button class="p-2 border border-gray-700 rounded-full hover:bg-slate-200">
                        <svg class="w-6 h-6 text-gray-800" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                            width="24" height="24" fill="none" viewBox="0 0 24 24">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M12.01 6.001C6.5 1 1 8 5.782 13.001L12.011 20l6.23-7C23 8 17.5 1 12.01 6.002Z" />
                        </svg>

                    </button>
                </div>



            </div>
            <button class="border border-black text-black w-full mt-3 py-2.5 text-sm font-bold hover:bg-slate-200">2
                Show More
            </button>

        </div>

    </div>
</template>
