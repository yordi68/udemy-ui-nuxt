<!-- components/Navbar.vue -->
<template>
    <nav class="bg-white shadow-sm">
        <div class="px-6 mx-auto flex justify-between items-center gap-8 py-4">
            <a href="/" class="flex items-center font-medium text-3xl">
                <span class="text-purple-500">U</span>
                <span>demy</span>
            </a>
            <a href="#" class="flex items-center space-x-2 text-black hover:text-purple-600">
                <span>Categories</span>
            </a>
            <div class="relative flex items-center flex-1">
                <input type="text"
                    class="bg-gray-100 w-full rounded-full py-3 border border-black px-4 pl-12 outline-none focus:border-purple-600  text-gray-600"
                    placeholder="Search for anything" />
                <svg class="w-5 h-5 absolute left-4 text-gray-600" viewBox="0 0 24 24" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M21 21L15 15M17 10C17 13.866 13.866 17 10 17C6.13401 17 3 13.866 3 10C3 6.13401 6.13401 3 10 3C13.866 3 17 6.13401 17 10Z"
                        stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
                </svg>
            </div>
            <a href="#" class="flex items-center space-x-2 text-black hover:text-purple-600 text-sm">

                <span>Udemy Business</span>
            </a>
            <a href="#" class="flex items-center space-x-2 text-black hover:text-purple-600 text-sm">

                <span>Teach on Udemy</span>
            </a>
                <div class="flex items-center space-x-3 px-2">
                    <a href="#" class="text-black hover:text-purple-600">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z">
                            </path>
                        </svg>
                    </a>
                    <button
                        class="text-black text-sm hover:text-gray-800 font-medium p-3 border border-gray-500 hover:bg-slate-200">
                        Log in
                    </button>
                    <button
                        class="bg-black text-sm text-white px-4  hover:bg-gray-800 p-3 border border-gray-500 font-medium">
                        Sign up
                    </button>
                    <a href="#"
                        class="text-black text-sm hover:text-gray-900 p-3 border border-gray-500 hover:bg-slate-200">
                        <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" fill="currentColor"
                            class="bi bi-globe" viewBox="0 0 16 16">
                            <path
                                d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8m7.5-6.923c-.67.204-1.335.82-1.887 1.855A8 8 0 0 0 5.145 4H7.5zM4.09 4a9.3 9.3 0 0 1 .64-1.539 7 7 0 0 1 .597-.933A7.03 7.03 0 0 0 2.255 4zm-.582 3.5c.03-.877.138-1.718.312-2.5H1.674a7 7 0 0 0-.656 2.5zM4.847 5a12.5 12.5 0 0 0-.338 2.5H7.5V5zM8.5 5v2.5h2.99a12.5 12.5 0 0 0-.337-2.5zM4.51 8.5a12.5 12.5 0 0 0 .337 2.5H7.5V8.5zm3.99 0V11h2.653c.187-.765.306-1.608.338-2.5zM5.145 12q.208.58.468 1.068c.552 1.035 1.218 1.65 1.887 1.855V12zm.182 2.472a7 7 0 0 1-.597-.933A9.3 9.3 0 0 1 4.09 12H2.255a7 7 0 0 0 3.072 2.472M3.82 11a13.7 13.7 0 0 1-.312-2.5h-2.49c.062.89.291 1.733.656 2.5zm6.853 3.472A7 7 0 0 0 13.745 12H11.91a9.3 9.3 0 0 1-.64 1.539 7 7 0 0 1-.597.933M8.5 12v2.923c.67-.204 1.335-.82 1.887-1.855q.26-.487.468-1.068zm3.68-1h2.146c.365-.767.594-1.61.656-2.5h-2.49a13.7 13.7 0 0 1-.312 2.5m2.802-3.5a7 7 0 0 0-.656-2.5H12.18c.174.782.282 1.623.312 2.5zM11.27 2.461c.247.464.462.98.64 1.539h1.835a7 7 0 0 0-3.072-2.472c.218.284.418.598.597.933M10.855 4a8 8 0 0 0-.468-1.068C9.835 1.897 9.17 1.282 8.5 1.077V4z" />
                        </svg>
                    </a>
                </div>
        </div>
    </nav>
</template>