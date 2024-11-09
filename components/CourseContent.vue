<template>
    <div class="py-8 w-[60%] mx-auto flex flex-col items-start text-gray-800">
        <div class="w-[67%]">
            <h2 class="text-3xl font-bold mb-4 font-sans">Course content</h2>
            <div class="flex justify-between items-center mb-4">
                <p class="text-sm text-gray-700">
                    75 sections • 731 lectures • 74h 13m total length
                </p>
                <button @click="expandAll = !expandAll"
                    class="text-purple-700 font-sans hover:underline text-sm font-bold">
                    {{ expandAll ? 'Collapse all Courses' : 'Expand all Courses' }}
                </button>
            </div>


            <div v-for="(section, index) in courseContent" :key="index" class="">
                <div @click="toggleSection(index)" :class="[
                    'flex justify-between items-center cursor-pointer border-gray-300 py-4 pl-6 pr-4 bg-gray-50',
                    section.isExpanded || expandAll || index === courseContent.length - 1 ? 'border-l border-r border-t border-b' : 'border-l border-r border-t'
                ]">
                    <div class="flex items-center">
                        <svg v-if="section.isExpanded" class="w-4 h-4 mr-3" fill="none" stroke="currentColor"
                            viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 15l7-7 7 7">
                            </path>
                        </svg>
                        <svg v-else class="w-4 h-4 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7">
                            </path>
                        </svg>
                        <h3 class=" font-bold">{{ section.title }}</h3>
                    </div>
                    <span class="text-gray-800 text-sm">{{ section.duration }}</span>
                </div>
                <div v-if="section.isExpanded || expandAll"
                    :class="['py-4 px-4 border-l border-r border-gray-300', index === courseContent.length - 1 ? 'border-b' : '']">
                    <div v-for="(item, itemIndex) in section.items" :key="itemIndex"
                        class="flex items-center px-4 w-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                            class="bi bi-camera-video mr-4" viewBox="0 0 16 16">
                            <path fill-rule="evenodd"
                                d="M0 5a2 2 0 0 1 2-2h7.5a2 2 0 0 1 1.983 1.738l3.11-1.382A1 1 0 0 1 16 4.269v7.462a1 1 0 0 1-1.406.913l-3.111-1.382A2 2 0 0 1 9.5 13H2a2 2 0 0 1-2-2zm11.5 5.175 3.5 1.556V4.269l-3.5 1.556zM2 4a1 1 0 0 0-1 1v6a1 1 0 0 0 1 1h7.5a1 1 0 0 0 1-1V5a1 1 0 0 0-1-1z" />
                        </svg>

                        <div class="flex items-center justify-between w-full ">
                            <a v-if="item.type === 'video'" :href="item.preview"
                                class="text-purple-600 hover:underline text-sm flex-grow">{{ item.title }}</a>
                            <span v-else class="text-sm flex-grow">{{ item.title }}</span>
                            <span class="text-sm">{{ item.duration }}</span>
                        </div>
                    </div>
                </div>
            </div>

            <button class="border border-black text-black w-full mt-3 py-2.5 text-sm font-bold hover:bg-slate-200">2 More Sections</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CourseContent',
    data() {
        return {
            expandAll: false,
            courseContent: [
                {
                    title: 'Course Orientation',
                    duration: '10 lectures • 31min',
                    items: [
                        { title: 'Welcome To The Course!', type: 'video', preview: '#', duration: '3:15' },
                        { title: 'Joining The Community Chat & Groups', type: 'text', duration: '4:20' },
                        { title: 'Curriculum Walkthrough', type: 'video', preview: '#', duration: '4:05' },
                        { title: 'When Was The Course Last Updated?', type: 'video', preview: '#', duration: '2:50' },
                        { title: 'Course Change Log', type: 'video', preview: '#', duration: '3:30' },
                        { title: 'Will I Get A Job?', type: 'video', preview: '#', duration: '4:15' },
                        { title: 'Accessing Course Code & Slides', type: 'video', preview: '#', duration: '3:45' },
                        { title: 'Tips On The Interactive Coding Exercises', type: 'text', duration: '5:00' },
                        { title: 'Course Coding Exercise Solutions', type: 'text', duration: '6:20' },
                        { title: 'Migrating From The Old Version Of This Course', type: 'text', duration: '3:10' }
                    ],
                    isExpanded: false
                },
                {
                    title: 'An Introduction to Web Development',
                    duration: '8 lectures • 40min',
                    items: [
                        { title: 'Introduction to the Web', type: 'video', preview: '#', duration: '5:05' },
                        { title: 'How the Web Works', type: 'video', preview: '#', duration: '4:45' },
                        { title: 'Web Browsers and the Document Object Model (DOM)', type: 'video', preview: '#', duration: '5:20' },
                        { title: 'Introduction to HTML', type: 'video', preview: '#', duration: '4:30' },
                        { title: 'Introduction to CSS', type: 'video', preview: '#', duration: '4:50' },
                        { title: 'Introduction to JavaScript', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'Web Development Workflow', type: 'video', preview: '#', duration: '4:55' },
                        { title: 'Hosting and Deploying Your Web Applications', type: 'video', preview: '#', duration: '5:00' }
                    ],
                    isExpanded: false
                },
                {
                    title: 'HTML: The Essentials',
                    duration: '13 lectures • 1hr 3min',
                    items: [
                        { title: 'HTML Syntax and Structure', type: 'video', preview: '#', duration: '4:30' },
                        { title: 'HTML Headings and Paragraphs', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'HTML Links and Anchors', type: 'video', preview: '#', duration: '4:40' },
                        { title: 'HTML Images and Media', type: 'video', preview: '#', duration: '5:25' },
                        { title: 'HTML Lists', type: 'video', preview: '#', duration: '4:50' },
                        { title: 'HTML Tables', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'HTML Forms', type: 'video', preview: '#', duration: '4:55' },
                        { title: 'HTML Divs and Spans', type: 'video', preview: '#', duration: '5:05' },
                        { title: 'HTML Semantic Elements', type: 'video', preview: '#', duration: '4:45' },
                        { title: 'HTML Accessibility', type: 'video', preview: '#', duration: '5:00' },
                        { title: 'HTML Document Structure', type: 'video', preview: '#', duration: '4:30' },
                        { title: 'HTML Validation and Best Practices', type: 'video', preview: '#', duration: '4:50' },
                        { title: 'HTML Developer Tools', type: 'video', preview: '#', duration: '4:40' }
                    ],
                    isExpanded: false
                },
                {
                    title: 'HTML: Next Steps & Semantics',
                    duration: '9 lectures • 1hr 1min',
                    items: [
                        { title: 'HTML5 Semantic Elements', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'HTML5 Structural Elements', type: 'video', preview: '#', duration: '4:30' },
                        { title: 'HTML5 Audio and Video', type: 'video', preview: '#', duration: '5:20' },
                        { title: 'HTML5 Forms and Validations', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'HTML5 APIs and Offline Capabilities', type: 'video', preview: '#', duration: '5:00' },
                        { title: 'HTML5 Microdata and Schema.org', type: 'video', preview: '#', duration: '4:45' },
                        { title: 'HTML5 Accessibility and ARIA', type: 'video', preview: '#', duration: '5:05' },
                        { title: 'HTML5 Responsive Design', type: 'video', preview: '#', duration: '4:50' },
                        { title: 'HTML5 Best Practices and Trends', type: 'video', preview: '#', duration: '5:10' }
                    ],
                    isExpanded: false
                },
                {
                    title: 'HTML: Forms & Tables',
                    duration: '17 lectures • 1hr 45min',
                    items: [
                        { title: 'HTML Form Basics', type: 'video', preview: '#', duration: '5:00' },
                        { title: 'HTML Form Elements', type: 'video', preview: '#', duration: '5:20' },
                        { title: 'HTML Form Validation', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'HTML Form Accessibility', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'HTML Form Styling', type: 'video', preview: '#', duration: '5:25' },
                        { title: 'HTML Form Submission and Server Integration', type: 'video', preview: '#', duration: '5:30' },
                        { title: 'HTML Table Basics', type: 'video', preview: '#', duration: '5:00' },
                        { title: 'HTML Table Structure and Semantics', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'HTML Table Styles and Layouts', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'HTML Table Accessibility', type: 'video', preview: '#', duration: '5:20' },
                        { title: 'HTML Table Advanced Features', type: 'video', preview: '#', duration: '5:25' },
                        { title: 'HTML Form and Table Best Practices', type: 'video', preview: '#', duration: '5:30' },
                        { title: 'HTML Form and Table Real-World Examples', type: 'video', preview: '#', duration: '5:20' },
                        { title: 'HTML Form and Table Troubleshooting', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'HTML Form and Table Resources', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'HTML Form and Table Challenges', type: 'video', preview: '#', duration: '5:25' },
                        { title: 'HTML Form and Table Wrap-Up', type: 'video', preview: '#', duration: '5:30' }
                    ],
                    isExpanded: false
                },
                {
                    title: 'CSS: The Very Basics',
                    duration: '11 lectures • 1hr',
                    items: [
                        { title: 'Introduction to CSS', type: 'video', preview: '#', duration: '5:00' },
                        { title: 'CSS Syntax and Selectors', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'CSS Properties and Values', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'CSS Inheritance and Specificity', type: 'video', preview: '#', duration: '5:20' },
                        { title: 'CSS Units and Measurements', type: 'video', preview: '#', duration: '5:25' },
                        { title: 'CSS Colors and Backgrounds', type: 'video', preview: '#', duration: '5:00' },
                        { title: 'CSS Fonts and Typography', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'CSS Box Model', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'CSS Margin and Padding', type: 'video', preview: '#', duration: '5:00' },
                        { title: 'CSS Border and Outline', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'CSS Debugging and Best Practices', type: 'video', preview: '#', duration: '5:20' }
                    ],
                    isExpanded: false
                },
                {
                    title: 'The World of CSS Selectors',
                    duration: '14 lectures • 1hr 10min',
                    items: [
                        { title: 'CSS Element Selectors', type: 'video', preview: '#', duration: '5:05' },
                        { title: 'CSS Class and ID Selectors', type: 'video', preview: '#', duration: '5:20' },
                        { title: 'CSS Descendant Selectors', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'CSS Child Selectors', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'CSS Adjacent Sibling Selectors', type: 'video', preview: '#', duration: '5:25' },
                        { title: 'CSS General Sibling Selectors', type: 'video', preview: '#', duration: '5:30' },
                        { title: 'CSS Attribute Selectors', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'CSS Pseudo-class Selectors', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'CSS Pseudo-element Selectors', type: 'video', preview: '#', duration: '5:20' },
                        { title: 'CSS Combinators', type: 'video', preview: '#', duration: '5:25' },
                        { title: 'CSS Selector Specificity', type: 'video', preview: '#', duration: '5:15' },
                        { title: 'CSS Selector Performance', type: 'video', preview: '#', duration: '5:10' },
                        { title: 'CSS Selector Best Practices', type: 'video', preview: '#', duration: '5:30' },
                        { title: 'CSS Selector Resources and Tools', type: 'video', preview: '#', duration: '5:20' }
                    ],
                    isExpanded: false
                }
            ]
        }
    },
    methods: {
        toggleSection(index) {
            this.courseContent[index].isExpanded = !this.courseContent[index].isExpanded;
        }
    }
}
</script>