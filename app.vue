<!-- <template>
  <div class="mx-64">
    <instructor-profile />
    <review-card />
    <course-review-modal />
    <course-listing />
  </div>
  <futer />
</template> -->

<script setup>

// import ExploreCourse from '@/components/ExploreCourse.vue'
// import Navbar from '@/components/Navbar.vue'
// import HeroSection from '@/components/HeroSection.vue'
// import CourseList from '@/components/CourseList.vue'
// import CourseDescription from '@/components/CourseDescription.vue'
// import FeaturedReview from '@/components/FeaturedReview.vue'
// import Recommendations from '@/components/Recommendations.vue'
// import RightSideBar from './components/RightSideBar.vue';

</script>



<!-- pages/index.vue -->
<template>
    <div>
    <!-- <Navbar /> -->
        <div class="relative">
          <Nuvbar />
          <HeroSection />
          <RightSideBar />

          <CourseList />
          <ExploreCourse />
          <CourseContent />
          <CourseDescription />
          <FeaturedReview />
          <Recommendations />
          <FrequentlyBoughtTogether />

          <instructor-profile />
          <review-card />
          <course-review-modal />
          <course-listing />
      </div>
    <futer />
  </div>
</template>

<style scoped>
div {
  font-family: Poppins, Roboto, sans-serif;
}
</style>
