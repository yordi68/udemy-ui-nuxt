<template>
    <div :class="['py-8', scrolled ? '-mt-[580px]' : '']">
        <div class="what-you-learn w-[60%] mx-auto flex flex-col items-start text-gray-800">
            <div class="border border-gray-300 w-[67%] p-4">
                <h2 class="text-2xl font-bold mb-4 font-sans">What you'll learn</h2>
                <div class="grid grid-cols-2 gap-4">
                    <div v-for="(item, index) in visibleItems" :key="index" class="flex items-start">
                        <svg class="w-4 h-4 mr-3 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7">
                            </path>
                        </svg>
                        <span class="text-sm">{{ item }}</span>
                    </div>
                </div>
                <button @click="toggleShowMore" class="font-bold text-purple-600 hover:underline pl-2 mt-4">
                    {{ showMoreButtonText }}
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            allItems: [
                'The ins and outs of HTML5, CSS3, and Modern JavaScript for 2021',
                'Create responsive, accessible, and beautiful layouts',
                'Continue to learn and grow as a developer, long after the course ends',
                'Create a complicated yelp-like application from scratch',
                'Make REAL web applications using cutting-edge technologies',
                'Create static HTML and CSS portfolio sites',                
                'Recognize and prevent common security exploits like SQL-Injection & XSS',
                'Create a blog application from scratch using Node, Express, and MongoDB',
                'Deploy your applications and work with cloud databases',
                'Think like a developer, Become an expert at',
                'Dive deep into modern JavaScript features and techniques',
                'Learn how to build scalable and maintainable web applications',
                'Implement advanced state management with Vuex or Redux',
                'Explore the latest web development tools and workflows',
                'Build and deploy production-ready web applications',
                'Optimize web performance and improve user experience',
                'Collaborate with other developers using Git and GitHub',
                'Prepare for technical interviews and land your dream job',
                'Master the principles of test-driven development (TDD)',
                'Integrate third-party APIs and data sources',
                'Understand and apply design patterns in your projects',
                'Utilize modern CSS techniques like Flexbox and Grid',
                'Explore the latest web framework and library trends',
                'Become proficient in server-side technologies like Node.js',
                'Learn to debug and troubleshoot complex web applications'
            ],
            visibleItemsCount: 10,
            showMoreButtonText: 'Show more',
            scrolled: false // Track scroll state
        }
    },
    computed: {
        visibleItems() {
            return this.allItems.slice(0, this.visibleItemsCount)
        }
    },
    methods: {
        toggleShowMore() {
            if (this.visibleItemsCount === this.allItems.length) {
                this.visibleItemsCount = 10
                this.showMoreButtonText = 'Show more'
            } else {
                this.visibleItemsCount = this.allItems.length
                this.showMoreButtonText = 'Show less'
            }
        },
        handleScroll() {
            // Add the -mt-96 class when the user has scrolled 100px or more
            this.scrolled = window.scrollY > 250
        }
    }, 
    mounted() {
        window.addEventListener('scroll', this.handleScroll)
    },
    beforeUnmount() {
        window.removeEventListener('scroll', this.handleScroll)
    }
}
</script>
