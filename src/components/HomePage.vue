<template>
  <div class="grid md:grid-cols-2 grod-cols-1   ">
    <div class="mx-auto my-20  md:mt-56">
        <h1 class="md:text-6xl  text-4xl">DO YOU WANT LEARN?</h1>
           <div class="justify-center flex mt-10">
              <button
                class="rounded-full 
                border-solid 
                border-2 
                p-3 
                bg-blue-500 
                text-white
                hover:bg-blue-700
                  hover:shadow-lg
                  ">
              <router-link to="/contact"> <h2 class="text-2xl"> Contact us</h2></router-link>
              </button>
           </div>
    </div>
     <div>
       <img src="../assets/section.img.jpg" alt="">
     </div>
  </div>
  <!-- SEZIONE 2-->
 <section class="grid md:grid-cols-2 bg-blue-500 grid-cols-1 ">
   <div class="md:text-2xl text-1xl py-4">
     <h1>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem impedit quos suscipit quis facilis alias voluptate. Dignissimos accusantium possimus dolorum ea, sunt vel reprehenderit modi labore nulla, suscipit doloribus delectus! Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae sit, omnis atque officia ut commodi aliquam voluptates ab, corrupti minus fugit. Cupiditate nihil expedita nam quas nesciunt cumque fugit perspiciatis.</h1>
   </div>
   <div class=" m-auto h-20">
    <span class="md:text-8xl text-5xl text-white"><h2>{{typeValue}}</h2></span>  
</div>
 </section>

 <!-- SEZIONE 3-->
 <section class="bg-white dark:bg-gray-900">
  <div class="container px-6 py-10 mx-auto">      
      <h1 class="mt-4  xl:mt-6  text-2xl">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nostrum quam voluptatibus
       </h1>
      
      <div class="grid grid-cols-1 gap-8 mt-8 xl:mt-12 xl:gap-12 md:grid-cols-2 xl:grid-cols-3">
          <div class="p-8 space-y-3 border-2 border-blue-400  rounded-xl">
              <span class="inline-block text-blue-500 ">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 3.055A9.001 9.001 0 1020.945 13H11V3.055z" />
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.488 9H15V3.512A9.025 9.025 0 0120.488 9z" />
                </svg>
              </span>

              <h1 class="text-2xl font-semibold text-gray-700 capitalize ">Javascript</h1>

              <p class="text-gray-500 ">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident ab nulla quod dignissimos vel non corrupti doloribus voluptatum eveniet
              </p>
          </div>

          <div class="p-8 space-y-3 border-2 border-blue-400  rounded-xl">
            <span class="inline-block text-blue-500 ">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z" />
            </svg>
              </span>

              <h1 class="text-2xl font-semibold text-gray-700 capitalize">HTML</h1>

              <p class="text-gray-500 dark:text-gray-300">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident ab nulla quod dignissimos vel non corrupti doloribus voluptatum eveniet
              </p>
          </div>

          <div class="p-8 space-y-3 border-2 border-blue-400 dark:border-blue-300 rounded-xl">
              <span class="inline-block text-blue-500 ">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
                </svg>
              </span>

              <h1 class="text-2xl font-semibold text-gray-700 capitalize">CSS</h1>

              <p class="text-gray-500 dark:text-gray-300">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident ab nulla quod dignissimos vel non corrupti doloribus voluptatum eveniet
              </p>
          </div>
      </div>
  </div>
</section>
 
</template>

<script>
import {ref} from 'vue'

export default {
  setup() {
  let typeValue= ref('')
  let typeStatus= ref(false)
  let typeArray= ['Javascript', 'CSS', 'HTML']
  let typingSpeed= ref(200)
  let erasingSpeed= ref(100)
  let newTextDelay= ref(2000)
  let typeArrayIndex= ref(0)
  let charIndex= ref(0)
  setTimeout(typeText,newTextDelay.value + 200);
  console.log(typeArrayIndex.value)
  function  typeText() {
        if(charIndex.value < typeArray[typeArrayIndex.value].length) {
          if(!typeStatus.value)
            typeStatus.value = true;
              typeValue.value += typeArray[typeArrayIndex.value].charAt(charIndex.value);
                charIndex.value += 1;
                  setTimeout(typeText, typingSpeed.value)
           }
        else {
          typeStatus.value = false;
            setTimeout(eraseText, newTextDelay.value)
        }
      }
  function  eraseText() {
        if(charIndex.value > 0) {
          if(!typeStatus.value)
            typeStatus.value = true;
          typeValue.value = typeArray[typeArrayIndex.value].substring(0, charIndex.value - 1);
          charIndex.value -= 1;
          setTimeout(eraseText, erasingSpeed.value)
        }
        else {
          typeStatus.value = false;
          typeArrayIndex.value += 1;
        if(typeArrayIndex.value >= typeArray.length)
            typeArrayIndex.value = 0;
          setTimeout(typeText, typingSpeed.value + 1000)
        }
      }
  return{
      typeValue,
      typeArray,
      typingSpeed,
      erasingSpeed,
      newTextDelay,
      typeArrayIndex,
      charIndex,
      }
  }
}
  
 

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h2{
    font-family: 'Merriweather', serif;
  }

</style>
