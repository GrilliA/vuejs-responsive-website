<template>
        <footer class="text-white body-font bg-blue-500">
          <div class="container px-5 py-10 mx-auto flex md:items-center lg:items-start md:flex-row md:flex-nowrap flex-wrap flex-col">
           
            <div class="flex-grow flex flex-wrap md:pl-20 -mb-10 md:mt-0 mt-10 md:text-left text-center">
              <div class="lg:w-1/4 md:w-1/2 w-full px-4">
                <h2 class=" font-bold text-white tracking-widest text-md mb-3">Categorie</h2>
                <nav class="list-none mb-10">
                  <li>
                    <router-link class="text-white hover:text-red-300" to="/">Home</router-link>
                  </li>
                  <li>
                    <router-link class="text-white hover:text-red-300" to="/contact">Contatti</router-link>
                  </li>   
                </nav>
              </div>        
            </div>
            <div class="flex-grow flex flex-wrap md:pl-20 -mb-10 md:mt-0 mt-10 md:text-left text-center">
                <div class="lg:w-1/4 md:w-1/2 w-full px-4">
                  <h2 class=" font-bold text-white tracking-widest text-md mb-3">Aiuto</h2>
                  <nav class="list-none mb-10">
                    <li>
                      <router-link class="text-white hover:text-red-300" to="#">test</router-link>
                    </li>
                    <li>
                      <router-link class="text-white hover:text-red-300" to="#">test</router-link>
                    </li>   
                  </nav>
                </div>        
              </div>
              <div class="flex-grow flex flex-wrap md:pl-20 -mb-10 md:mt-0 mt-10 md:text-left text-center">
                <div class="lg:w-1/4 md:w-1/2 w-full px-4">
                  <h2 class=" font-bold text-white tracking-widest text-md mb-3">Servizi</h2>
                  <nav class="list-none mb-10">
                    <li>
                      <router-link class="text-white" to="#">test</router-link>
                    </li>
                    <li>
                      <router-link class="text-white" to="#">test</router-link>
                    </li>   
                  </nav>
                </div>        
              </div>
          </div>
          <div class="bg-blue-800">
            <div class="container mx-auto py-4 px-5 flex flex-wrap flex-col sm:flex-row">
              <p class="text-white text-sm text-center sm:text-left">© 2022 Alessio Grilli
              </p>
              <span class="inline-flex sm:ml-auto sm:mt-0 mt-2 justify-center sm:justify-start">
                <a class="text-white">
                  <svg fill="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-5 h-5" viewBox="0 0 24 24">
                    <path d="M18 2h-3a5 5 0 00-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 011-1h3z"></path>
                  </svg>
                </a>
                <a class="ml-3 text-white">
                  <svg fill="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-5 h-5" viewBox="0 0 24 24">
                    <path d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"></path>
                  </svg>
                </a>
                <a class="ml-3 text-white">
                  <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-5 h-5" viewBox="0 0 24 24">
                    <rect width="20" height="20" x="2" y="2" rx="5" ry="5"></rect>
                    <path d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37zm1.5-4.87h.01"></path>
                  </svg>
                </a>
                <a class="ml-3 text-white">
                  <svg fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="0" class="w-5 h-5" viewBox="0 0 24 24">
                    <path stroke="none" d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"></path>
                    <circle cx="4" cy="4" r="2" stroke="none"></circle>
                  </svg>
                </a>
              </span>
            </div>
          </div>
        </footer>
</template>