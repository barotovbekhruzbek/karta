<template>
 
    <div>
      <Navbar />
      <div class="container app">
        <TheTitle />
        <ContactInfo />
      </div>
    </div>
  
</template>


<script>
import Navbar from './components/Navbar.vue'
import TheTitle from './components/The-title.vue'
import ContactInfo from './components/Contact-info.vue'

export default {
  components: {
    Navbar,
    TheTitle,
    ContactInfo,
  }
}
</script>


<style>
  body{
    height: 200vh;
  }

  .container{
    width: 100%;
    max-width: 1140px;
    padding: 0 15px;
    margin: 0 auto;
  }
  .app{
    padding-top: 200px;
  }

</style>