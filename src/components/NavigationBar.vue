<template>
  
    <header class="bg-blue-600   sm:px-8 sm:py-3 ">
      <div class="flex items-center justify-between   px-4 py-3 sm:p-0">
        <div>
          <svg xmlns="http://www.w3.org/2000/svg" class="h-12 w-12 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
          </svg>
        </div>
        <nav class="hidden sm:flex sm:justify-end" >
          <router-link to="/"  class="block px-4 py-1  text-white font-semibold rounded hover:bg-gray-800">Home</router-link>
          <router-link to="/contact"  class="mt-1 block px-4 py-1  text-white font-semibold rounded hover:bg-gray-800 sm:mt-0 sm:ml-2">Contact</router-link>     
        </nav>
     
        <div class="sm:hidden">
          
          <button @click="isOpen = !isOpen" type="button" class="block text-gray-200 hover:text-white focus:text-white focus:outline-none">
            <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
              <path v-if="isOpen" fill-rule="evenodd" d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"/>
              <path v-if="!isOpen" fill-rule="evenodd" d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"/>
            </svg>
          </button>
        </div>
        </div>
      
      
        
       
      <transition  
      @before-enter="beforeEnter"
      @enter="enter"
      @leave="leave"
      >
        <nav class="px-2 pt-2 pb-4 sm:hidden" v-if="isOpen"  >
          <router-link to="/" class="block px-2 py-1 text-white font-semibold rounded hover:bg-gray-800">Home</router-link>
          <router-link to="/contact" class="mt-1 block px-2 py-1 text-white font-semibold rounded hover:bg-gray-800 sm:mt-0 sm:ml-2">Contact</router-link>     
        </nav>
      </transition>
    </header>
  
</template>

<script>
  
import Velocity from 'velocity-animate'
import {ref} from 'vue'
export default {
  setup() {
    let isOpen = ref(false)

    function beforeEnter(el) {
      el.style.opacity = 0
      el.style.height = '0em'
    }
    function enter(el, done) {
      Velocity(
        el,
        { opacity: 1, height: '100%' },
        { duration: 1000, easing: 'easeOutCubic', complete: done }
      )
    }
    function   leave(el, done) {
      Velocity(
        el,
        { opacity: 0, height: '0em' },
        { duration: 800, easing: 'easeInCubic', complete: done }
      )
    }
    return{isOpen,beforeEnter,enter,leave}
  }

}
</script>

<style scoped>

</style>