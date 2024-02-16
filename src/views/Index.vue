<template>
  <section class="bg-gray-900 text-white">
    <div class="mx-auto max-w-screen-xl px-4 py-32 lg:h-screen">
      <div class="mx-auto max-w-3xl text-center">
        <h1 class="bg-gradient-to-r from-green-300 via-blue-500 to-purple-600 bg-clip-text text-3xl font-extrabold text-transparent sm:text-5xl">
          Knowladge Assistance
        </h1>

        <p class="mx-auto mt-4 max-w-xl sm:text-md/relaxed">
         Ontology Web Semantic
        </p>

        <div class="mt-8">
          <form class="flex items-center max-w-lg mx-auto">   
              <label for="voice-search" class="sr-only">Search</label>
              <div class="relative w-full">
                  <div class="absolute inset-y-0 start-0 flex items-center ps-3 pointer-events-none">
                      <svg class="w-4 h-4 text-gray-500 dark:text-gray-400" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 21 21">
                          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11.15 5.6h.01m3.337 1.913h.01m-6.979 0h.01M5.541 11h.01M15 15h2.706a1.957 1.957 0 0 0 1.883-1.325A9 9 0 1 0 2.043 11.89 9.1 9.1 0 0 0 7.2 19.1a8.62 8.62 0 0 0 3.769.9A2.013 2.013 0 0 0 13 18v-.857A2.034 2.034 0 0 1 15 15Z"/>
                      </svg>
                  </div>
                  <input type="text" id="voice-search" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full ps-10 p-2.5  dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Search Mockups, Logos, Design Templates..." required />
                  <button type="button" class="absolute inset-y-0 end-0 flex items-center pe-3">
                      <svg class="w-4 h-4 text-gray-500 dark:text-gray-400 hover:text-gray-900 dark:hover:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 16 20">
                          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 7v3a5.006 5.006 0 0 1-5 5H6a5.006 5.006 0 0 1-5-5V7m7 9v3m-3 0h6M7 1h2a3 3 0 0 1 3 3v5a3 3 0 0 1-3 3H7a3 3 0 0 1-3-3V4a3 3 0 0 1 3-3Z"/>
                      </svg>
                  </button>
              </div>
              <button type="submit" class="inline-flex items-center py-2.5 px-3 ms-2 text-sm font-medium text-white bg-blue-700 rounded-lg border border-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                  <svg class="w-4 h-4 me-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 20">
                      <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z"/>
                  </svg>Search
              </button>
          </form>
        </div>
      </div>
      <article class="rounded-xl border border-gray-700 bg-gray-800 my-32 lg:mx-[100px] p-10">
        <div class="flex items-center gap-4">
          <img
            alt=""
            src="https://images.unsplash.com/photo-1614644147724-2d4785d69962?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=928&q=80"
            class="size-16 rounded-full object-cover"
          />

          <div>
            <h3 class="text-lg font-medium text-white">Wikipedia</h3>

            <div class="flow-root">
              <ul class="-m-1 flex flex-wrap">
                <li class="p-1 leading-none">
                  <a href="#" class="text-xs font-medium text-gray-300"> wikipedia.org</a>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <ul class="mt-4 space-y-2">
          <li>
            <a href="#" class="block h-full rounded-lg border border-gray-700 p-4 hover:border-pink-600">
              <strong class="font-medium text-white">Project A</strong>

              <p class="mt-1 text-xs font-medium text-gray-300">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime consequuntur deleniti,
                unde ab ut in!
              </p>
            </a>
          </li>

          <li>
            <a href="#" class="block h-full rounded-lg border border-gray-700 p-4 hover:border-pink-600">
              <strong class="font-medium text-white">Project B</strong>

              <p class="mt-1 text-xs font-medium text-gray-300">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente cumque saepe sit.
              </p>
            </a>
          </li>
        </ul>
      </article>
    </div>
  </section>



</template>

<script setup>
import { CalendarDaysIcon, HandRaisedIcon } from '@heroicons/vue/24/outline'
</script>

<script>

import axios from 'axios';
import config from '@/config';

export default {
  name: 'Example',
  data() {
    return {
      items: [],
    };
  },
  mounted() {
    axios.get(config.apiUrl+'/post')
      .then((response) => {
        this.items = response.data.data.data;
        console.log(this.items);
      })
      .catch((error) => {
        console.error('Error fetching data:', error);
      });
  },
};
</script>


