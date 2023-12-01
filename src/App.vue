<template>
  <div class="app" >
    <Navigation />
    <div class="block w-full h-full"  >
      <Home />
      <!-- <NewView /> -->
    </div>
  </div>
</template>

<script>
import Home from "./pages/HomeView.vue";
import Navigation from "./components/Navigation.vue";
export default {
  name: "App",
  components: {
    Home,
    Navigation
  },
};
</script>

<style scoped>
.app{
  padding: 0;
  margin: 0;
}
</style>

