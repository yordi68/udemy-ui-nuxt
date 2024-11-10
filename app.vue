<script setup>
import Header from '@/components/sections/Header.vue'
import CourseContent from '@/components/sections/CourseContent.vue'
import CourseOverview from '@/components/sections/CourseOverview.vue'
import FeaturedReview from '@/components/reviews/FeaturedReview.vue'
import ReviewCard from '@/components/reviews/ReviewCard.vue'
import CourseReviewModal from '@/components/reviews/CourseReviewModal.vue'
import CourseListing from '@/components/courses/CourseListing.vue'
</script>


<template>
  <div>
    <div class="relative">
      <Header />
      <CourseOverview />
      <CourseContent />

      <featured-review />

      <section id="additional-recommendations">
        <recommendations />
      </section>

      <instructor-profile />

      <section id="reviews-feedback">
        <review-card />
        <course-review-modal />
      </section>

      <course-listing />

    </div>
    <Footer />
  </div>
</template>

<style scoped>
div {
  font-family: Poppins, Roboto, sans-serif;
}
</style>
