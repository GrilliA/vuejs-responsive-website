<template>
  <NavigationBar />
  <router-view v-slot="{ Component }">
    <transition name="slide-fade" mode="out-in">
      <component :is="Component" />
    </transition>
  </router-view>
  <FooterBar />
</template>
<script>
  import NavigationBar from './components/NavigationBar.vue'
  import FooterBar from './components/FooterBar.vue'
  export default {
    components: {
      NavigationBar,
      FooterBar
    },
  }
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Merriweather:wght@700&display=swap');
.router-link-active{
  border-bottom: 3px solid white;
}

*,body{
  border: 0;
  padding: 0;
  margin: 0;
}

.slide-fade-enter {
      transform: translateX(10px);
      opacity: 0;
    }
    
.slide-fade-enter-active,
.slide-fade-leave-active {
      transition: all 0.2s ease;
    }
    
.slide-fade-leave-to {
      transform: translateX(-10px);
      opacity: 0;
    }
</style>
