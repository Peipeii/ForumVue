<template>
  <div id="restaurant-forum">
    <Navbar />
    <main class="mt-5">
      <router-view />
    </main>
  </div>
</template>

<script>
import 'bootstrap' // js
import 'bootstrap/dist/css/bootstrap.min.css'
import Navbar from './components/Navbar'

export default {
  components: {
    Navbar
  }
}
</script>