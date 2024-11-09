<template>
    <div class="w-[60%] mx-auto">
  <div class="border border-gray-300 w-[67%] p-6 text-gray-800">
    <h2 class="text-2xl font-bold mb-6">Frequently Bought Together</h2>
    <div class="flex flex-col  gap-6">
      <div class="flex items-start" v-for="course in courses" :key="course.id">
        <img src="/assets/images/sidebar.jpg" class="w-36 h-24  mr-4" :alt="course.title">
        
        <div class="flex-1">
          <h3 class="text-lg font-bold">{{ course.title }}</h3>
          <p class="text-xs text-gray-600 ">{{ course.description }}</p>
          <div class="flex items-center ">
            <span class="text-yellow-700">
                {{  course.rating }}
            </span>
            <div class="flex items-center text-yellow-500 mr-2">
              <svg class="w-5 h-5 fill-current" v-for="n in 5" :key="n" :class="{ 'text-gray-400': n > course.rating }">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            </div>
            <span class="text-sm text-gray-500">({{ course.numEnrollments }})</span>
        </div>
        </div>
        <p class="font-bold pl-16 pr-4">
            ${{course.price }}
        </p>
      </div>
    </div>
    <div class="flex justify-between mt-6">
      <p class="text-gray-900">Total: <span class="font-bold">${{ total }}</span></p>
      <button class="bg-purple-600 text-white px-4 py-2  ml-4 hover:bg-purple-700">
        Add all to cart
      </button>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  name: 'FrequentlyBoughtTogether',
  data() {
    return {
      courses: [
        {
          id: 1,
          title: 'User Experience (UX): The Ultimate Guide to Usability and UX',
          rating: 4.6,
          numEnrollments: 6620,
          price: 69.99,
          description: 'David Travis'
        },
        {
          id: 2,
          title: 'Usability Testing Boot Camp',
          rating: 4.6,
          numEnrollments: 842,
          price: 19.99,
          description: 'David Travis',
          isBestseller: true
        },
        {
          id: 3,
          title: 'How to carry out a usability expert review',
          rating: 4.5,
          numEnrollments: 638,
          price: 19.99,
          description: 'David Travis'
        }
      ]
    }
  },
  computed: {
    total() {
      return this.courses.reduce((acc, course) => acc + course.price, 0).toFixed(2);
    }
  }
}
</script>