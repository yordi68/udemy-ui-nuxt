<script setup>
const certifications = [
    'Amazon Web Services (AWS) Certifications',
    'Six Sigma Certifications',
    'Microsoft Certifications',
    'Cisco Certifications',
    'Tableau Certifications',
    'See all Certifications'
]

const webDevelopment = [
    'Web Development',
    'JavaScript',
    'React JS',
    'Angular',
    'Java'
]

const itCertifications = [
    'Amazon AWS',
    'AWS Certified Cloud Practitioner',
    'AZ-900: Microsoft Azure Fundamentals',
    'AWS Certified Solutions Architect - Associate',
    'Kubernetes'
]

const leadership = [
    'Leadership',
    'Management Skills',
    'Project Management',
    'Personal Productivity',
    'Emotional Intelligence'
]

const certificationsBySkill = [
    'Cybersecurity Certification',
    'Project Management Certification',
    'Cloud Certification',
    'Data Analytics Certification',
    'HR Management Certification',
    'See all Certifications'
]

const dataScience = [
    'Data Science',
    'Python',
    'Machine Learning',
    'ChatGPT',
    'Deep Learning'
]

const communication = [
    'Communication Skills',
    'Presentation Skills',
    'Public Speaking',
    'Writing',
    'PowerPoint'
]

const businessAnalytics = [
    'Microsoft Excel',
    'SQL',
    'Microsoft Power BI',
    'Data Analysis',
    'Business Analysis'
]

const bottomFooter = [
    {
        title: 'About',
        items: ['About us', 'Careers', 'Contact us', 'Blog', 'Investors']
    },
    {
        title: 'Discovery Udemy',
        items: ['Get the app', 'Teach on Udemy', 'Plans and Pricing', 'Affiliate', 'Help and Support']
    },
    {
        title: 'Udemy for Business',
        items: ['Udemy Business']
    },
    {
        title: 'Legal & Accessibility',
        items: ['Accessibility statement', 'Privacy policy', 'Sitemap', 'Terms']
    }
]
</script>


<template>
    <footer class="bg-[#1c1d1f] text-white">
        <div class="border-b border-gray-700">
            <div class="container flex flex-col items-center justify-between px-4 py-4 mx-auto md:flex-row">
                <p class="mb-4 text-sm md:mb-0">
                    Top companies choose <span class="text-purple-400">Udemy Business</span> to build in-demand career
                    skills.
                </p>
                <div class="flex flex-wrap items-center justify-center gap-4 text-gray-600 md:gap-8">


                    <svg class="nsdq-logo--default" width="85" height="24" viewBox="0 0 106 30" fill="none"
                        xmlns="http://www.w3.org/2000/svg" focusable="false" aria-hidden="true">
                        <path fill="gray" fill-rule="evenodd" clip-rule="evenodd"
                            d="M78.1281 22.8256C74.5111 22.8256 72.2639 20.7247 72.2639 17.3409C72.2639 13.8246 74.3374 11.6398 77.6759 11.6398L77.9581 11.6382C78.3755 11.6382 78.9524 11.6514 79.74 11.7517V7.50928H82.102V22.4441C82.102 22.4441 79.8589 22.8256 78.1281 22.8256ZM78.1076 13.5027C75.8219 13.5027 74.7106 14.7392 74.7106 17.2823C74.7106 19.5643 76.0503 20.9817 78.206 20.9817C78.6198 20.9817 79.0941 20.9559 79.74 20.8989V13.6537C79.0935 13.5508 78.5745 13.5027 78.1076 13.5027Z">
                        </path>
                        <path fill="gray" fill-rule="evenodd" clip-rule="evenodd"
                            d="M45.8108 22.485L39.4365 11.3324L39.4349 22.485H37.214V8.36816H40.3225L46.6968 19.421L46.6941 8.36816H48.9435V22.485H45.8108Z">
                        </path>
                        <path fill="gray" fill-rule="evenodd" clip-rule="evenodd"
                            d="M66.1111 22.7014C65.0383 22.7014 63.9186 22.5811 62.5857 22.3241L62.4441 22.2961V20.324L62.6552 20.3704C63.8286 20.6206 64.843 20.8369 65.8563 20.8369C66.677 20.8369 68.5858 20.706 68.5858 19.4975C68.5858 18.4827 67.2666 18.2289 66.2064 18.0257L66.1401 18.0125C65.9432 17.9735 65.7568 17.9365 65.5973 17.8964C64.0434 17.4916 62.3857 16.8847 62.3857 14.7965C62.3857 12.7605 63.9939 11.5927 66.7975 11.5927C68.1425 11.5927 69.1195 11.7383 69.9039 11.8555L70.2877 11.913V13.8244L70.0829 13.7891C69.1948 13.6249 68.1541 13.4566 67.1513 13.4566C66.04 13.4566 64.7161 13.6651 64.7161 14.6588C64.7161 15.482 65.7979 15.7179 67.0507 15.9908C68.8011 16.3728 70.9736 16.8483 70.9736 19.2426C70.9736 21.4406 69.2011 22.7014 66.1111 22.7014Z">
                        </path>
                        <path fill="gray" fill-rule="evenodd" clip-rule="evenodd"
                            d="M88.7257 22.7014C86.2811 22.7014 84.0196 22.2708 84.0196 19.1445C84.0196 15.7427 87.5176 15.7427 89.608 15.7427C89.817 15.7427 90.7993 15.7876 91.102 15.8013C91.0993 13.893 91.0735 13.4376 88.313 13.4376C87.2186 13.4376 86.0026 13.6556 84.9298 13.8476L84.725 13.8846V11.9995L84.865 11.971C86.1079 11.7167 87.3065 11.5927 88.5289 11.5927C91.2046 11.5927 93.4719 11.8634 93.4719 15.1902V22.4476L93.3087 22.4644C91.4557 22.6729 89.9833 22.7014 88.7257 22.7014ZM89.5485 17.4251C87.5334 17.4251 86.2848 17.7223 86.2848 19.2025C86.2848 20.915 87.8788 21.058 89.3727 21.058C89.9323 21.058 90.9362 20.9868 91.2431 20.9636V17.4832C90.8098 17.4668 89.6849 17.4251 89.5485 17.4251Z">
                        </path>
                        <path fill="gray" fill-rule="evenodd" clip-rule="evenodd"
                            d="M55.6178 22.7014C53.1731 22.7014 50.9117 22.2708 50.9117 19.1445C50.9117 15.7427 54.4097 15.7427 56.5001 15.7427C56.7085 15.7427 57.6913 15.7876 57.994 15.8013C57.9914 13.893 57.9656 13.4376 55.2051 13.4376C54.1107 13.4376 52.8952 13.6556 51.8218 13.8476L51.6171 13.8846V11.9995L51.7571 11.971C53.0005 11.7167 54.1986 11.5927 55.4209 11.5927C58.0967 11.5927 60.3639 11.8634 60.3639 15.1902V22.4476L60.2007 22.4644C58.3478 22.6729 56.8754 22.7014 55.6178 22.7014ZM56.4406 17.4251C54.4255 17.4251 53.1768 17.7223 53.1768 19.2025C53.1768 20.915 54.7708 21.058 56.2648 21.058C56.8243 21.058 57.8282 20.9868 58.1351 20.9636V17.4832C57.7019 17.4668 56.5769 17.4251 56.4406 17.4251Z">
                        </path>
                        <path fill="gray" fill-rule="evenodd" clip-rule="evenodd"
                            d="M102.868 27.2799V22.6501C101.946 22.7799 101.456 22.7799 101.061 22.7799C100.127 22.7799 99.0893 22.5762 98.2844 22.2342C96.4867 21.4859 95.4134 19.5808 95.4134 17.1374C95.4134 15.9157 95.7098 13.6861 97.6938 12.4844C98.6871 11.8881 99.8642 11.6332 101.63 11.6332C102.264 11.6332 103.118 11.6823 103.943 11.7303L105.283 11.7994V26.2081L102.868 27.2799ZM101.453 13.4966C99.0572 13.4966 97.8412 14.7215 97.8412 17.1374C97.8412 20.2447 99.6558 20.897 101.179 20.897C101.549 20.897 101.967 20.897 102.89 20.7803V13.5636C102.167 13.5145 101.835 13.4966 101.453 13.4966Z">
                        </path>
                        <path fill="gray" fill-rule="evenodd" clip-rule="evenodd"
                            d="M26.6726 0L18.8675 21.4961C18.6759 22.0265 18.1921 22.4138 17.612 22.4724V22.4851H25.8619C26.5089 22.4851 27.0616 22.0729 27.269 21.4961L35.0742 0H26.6726ZM16.9409 22.1567C17.4173 22.1567 17.8374 21.9203 18.0943 21.5593C18.1212 21.5218 18.2149 21.3899 18.2801 21.2099L21.1433 13.3225L19.4688 8.71643C19.255 8.20506 18.7502 7.84567 18.1622 7.84567C17.6863 7.84567 17.2657 8.08157 17.0088 8.44306C16.982 8.48001 16.8704 8.64835 16.823 8.79242L13.9609 16.6767L15.6423 21.3012C15.8602 21.8042 16.3587 22.1567 16.9409 22.1567ZM9.21221 7.51601H17.5522V7.52076C16.9326 7.54662 16.4077 7.94611 16.2066 8.50445L8.40206 30H0L7.80458 8.50445C8.01304 7.92764 8.56472 7.51601 9.21221 7.51601Z">
                        </path>
                    </svg>


                    <svg viewBox="0 0 40 21.6" width="36" height="22.2">
                        <path fill="gray" class="box-logo-svg"
                            d="M39.7 19.2c.5.7.4 1.6-.2 2.1-.7.5-1.7.4-2.2-.2l-3.5-4.5-3.4 4.4c-.5.7-1.5.7-2.2.2-.7-.5-.8-1.4-.3-2.1l4-5.2-4-5.2c-.5-.7-.3-1.7.3-2.2.7-.5 1.7-.3 2.2.3l3.4 4.5L37.3 7c.5-.7 1.4-.8 2.2-.3.7.5.7 1.5.2 2.2L35.8 14l3.9 5.2zm-18.2-.6c-2.6 0-4.7-2-4.7-4.6 0-2.5 2.1-4.6 4.7-4.6s4.7 2.1 4.7 4.6c-.1 2.6-2.2 4.6-4.7 4.6zm-13.8 0c-2.6 0-4.7-2-4.7-4.6 0-2.5 2.1-4.6 4.7-4.6s4.7 2.1 4.7 4.6c0 2.6-2.1 4.6-4.7 4.6zM21.5 6.4c-2.9 0-5.5 1.6-6.8 4-1.3-2.4-3.9-4-6.9-4-1.8 0-3.4.6-4.7 1.5V1.5C3.1.7 2.4 0 1.6 0 .7 0 0 .7 0 1.5v12.6c.1 4.2 3.5 7.5 7.7 7.5 3 0 5.6-1.7 6.9-4.1 1.3 2.4 3.9 4.1 6.8 4.1 4.3 0 7.8-3.4 7.8-7.7.1-4.1-3.4-7.5-7.7-7.5z">
                        </path>
                    </svg>



                    <svg viewBox="0 0 40 21.6" width="36" height="22.2">
                        <path fill="gray" class="box-logo-svg"
                            d="M39.7 19.2c.5.7.4 1.6-.2 2.1-.7.5-1.7.4-2.2-.2l-3.5-4.5-3.4 4.4c-.5.7-1.5.7-2.2.2-.7-.5-.8-1.4-.3-2.1l4-5.2-4-5.2c-.5-.7-.3-1.7.3-2.2.7-.5 1.7-.3 2.2.3l3.4 4.5L37.3 7c.5-.7 1.4-.8 2.2-.3.7.5.7 1.5.2 2.2L35.8 14l3.9 5.2zm-18.2-.6c-2.6 0-4.7-2-4.7-4.6 0-2.5 2.1-4.6 4.7-4.6s4.7 2.1 4.7 4.6c-.1 2.6-2.2 4.6-4.7 4.6zm-13.8 0c-2.6 0-4.7-2-4.7-4.6 0-2.5 2.1-4.6 4.7-4.6s4.7 2.1 4.7 4.6c0 2.6-2.1 4.6-4.7 4.6zM21.5 6.4c-2.9 0-5.5 1.6-6.8 4-1.3-2.4-3.9-4-6.9-4-1.8 0-3.4.6-4.7 1.5V1.5C3.1.7 2.4 0 1.6 0 .7 0 0 .7 0 1.5v12.6c.1 4.2 3.5 7.5 7.7 7.5 3 0 5.6-1.7 6.9-4.1 1.3 2.4 3.9 4.1 6.8 4.1 4.3 0 7.8-3.4 7.8-7.7.1-4.1-3.4-7.5-7.7-7.5z">
                        </path>
                    </svg>


                    <svg viewBox="0 0 200 36" width="100" height="24">
                        <g fill-rule="evenodd">
                            <g>
                                <g transform="translate(.347)">
                                    <path fill="gray"
                                        d="M185.945 17.513c2.693-.61 5.381.495 6.878 2.584l-11.905 2.693c.411-2.52 2.333-4.668 5.027-5.277zm6.944 9.91a6.57 6.57 0 01-3.979 2.679c-2.711.614-5.417-.51-6.908-2.626l11.942-2.702 1.945-.44 3.719-.841a11.782 11.782 0 00-.31-2.372c-1.513-6.426-8.055-10.432-14.611-8.949-6.556 1.484-10.644 7.896-9.13 14.321 1.513 6.426 8.055 10.433 14.61 8.95 3.864-.875 6.869-3.46 8.377-6.751l-5.655-1.269z">
                                    </path>
                                    <path fill="gray" id="logo-wordmark-brand_svg__Fill-10"
                                        d="M164.788 35.118V18.082h-3.677v-5.804h3.677V4.289h6.244v7.989h4.69v5.804h-4.69v17.036z">
                                    </path>
                                    <path fill="gray"
                                        d="M152.86 35.118h6.03v-22.84h-6.03v22.84zm-.785-30.853c0-2.114 1.667-3.7 3.825-3.7 2.157 0 3.775 1.586 3.775 3.7 0 2.115-1.618 3.748-3.775 3.748-2.158 0-3.825-1.633-3.825-3.748zM150.76 12.342c-3.082.16-4.9.633-6.75 1.973v-2.037h-6.026v22.84h6.026v-11.2c0-3.524.86-5.529 6.75-5.726v-5.85zM117.16 24.057c.15 3.333 3.051 6.128 6.602 6.128 3.601 0 6.552-2.942 6.552-6.422 0-3.432-2.95-6.373-6.552-6.373-3.551 0-6.452 2.843-6.602 6.128v.539zm-5.88 11.061V1.38l6.03-1.364v13.962c1.863-1.49 4.07-2.115 6.472-2.115 6.864 0 12.355 5.286 12.355 11.918 0 6.583-5.491 11.965-12.355 11.965-2.403 0-4.609-.624-6.472-2.114v1.487h-6.03z">
                                    </path>
                                    <path fill="gray" id="logo-wordmark-brand_svg__Fill-1"
                                        d="M98.445 35.118V17.965h-3.677v-5.687h3.677V4.283l6.244-1.413v9.408h4.69v5.687h-4.69v17.153z">
                                    </path>
                                    <path fill="gray"
                                        d="M87.394 35.118V22.915c0-4.421-2.402-5.382-4.805-5.382-2.402 0-4.805.913-4.805 5.286v12.299h-6.03v-22.84h6.03v1.699c1.324-.961 2.942-2.115 6.13-2.115 5.098 0 9.51 2.932 9.51 10.092v13.164h-6.03zM56.484 17.513c2.694-.61 5.382.495 6.878 2.584L51.458 22.79c.41-2.52 2.332-4.668 5.026-5.277zm6.945 9.91a6.57 6.57 0 01-3.98 2.679c-2.711.614-5.416-.51-6.907-2.626l11.942-2.702 1.944-.44 3.72-.841a11.782 11.782 0 00-.31-2.372c-1.514-6.426-8.056-10.432-14.612-8.949-6.556 1.484-10.644 7.896-9.13 14.321 1.513 6.426 8.055 10.433 14.611 8.95 3.863-.875 6.868-3.46 8.376-6.751l-5.654-1.269z">
                                    </path>
                                    <path fill="gray" id="logo-wordmark-brand_svg__Fill-2"
                                        d="M31.89 35.118l-9.364-22.84h6.57l5.932 15.49 5.982-15.49h6.57l-9.365 22.84z">
                                    </path>
                                    <path fill="gray"
                                        d="M10.703 17.507c2.694-.61 5.382.495 6.878 2.584L5.677 22.785c.41-2.52 2.332-4.668 5.026-5.278zm6.945 9.91a6.57 6.57 0 01-3.98 2.68c-2.71.613-5.416-.51-6.907-2.626l11.942-2.702 1.945-.44 3.718-.842a11.782 11.782 0 00-.31-2.371c-1.513-6.426-8.055-10.433-14.61-8.95C2.888 13.65-1.2 20.063.314 26.489c1.514 6.426 8.055 10.432 14.611 8.949 3.864-.874 6.869-3.46 8.376-6.75l-5.654-1.27z">
                                    </path>
                                </g>
                            </g>
                        </g>
                    </svg>


                </div>
            </div>
        </div>

        <div class="container px-4 py-12 mx-auto">
            <h2 class="mb-8 text-2xl font-bold">Explore top skills and certifications</h2>

            <div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
                <div>
                    <h3 class="mb-4 font-semibold">Certifications by Issuer</h3>
                    <ul class="space-y-2">
                        <li v-for="cert in certifications" :key="cert">
                            <a href="#" class="text-gray-300 hover:text-white">{{ cert }}</a>
                        </li>
                    </ul>
                </div>

                <div>
                    <h3 class="mb-4 font-semibold">Web Development</h3>
                    <ul class="space-y-2">
                        <li v-for="topic in webDevelopment" :key="topic">
                            <a href="#" class="text-gray-300 hover:text-white">{{ topic }}</a>
                        </li>
                    </ul>
                </div>

                <div>
                    <h3 class="mb-4 font-semibold">IT Certifications</h3>
                    <ul class="space-y-2">
                        <li v-for="cert in itCertifications" :key="cert">
                            <a href="#" class="text-gray-300 hover:text-white">{{ cert }}</a>
                        </li>
                    </ul>
                </div>

                <div>
                    <h3 class="mb-4 font-semibold">Leadership</h3>
                    <ul class="space-y-2">
                        <li v-for="skill in leadership" :key="skill">
                            <a href="#" class="text-gray-300 hover:text-white">{{ skill }}</a>
                        </li>
                    </ul>
                </div>
            </div>


        </div>

        <div class="border-t border-gray-700">
            <div class="container px-4 py-8 mx-auto">
                <div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
                    <div v-for="(section, index) in bottomFooter" :key="index">
                        <h3 class="mb-4 font-semibold">{{ section.title }}</h3>
                        <ul class="space-y-2">
                            <li v-for="item in section.items" :key="item">
                                <a href="#" class="text-gray-300 hover:text-white">{{ item }}</a>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>
