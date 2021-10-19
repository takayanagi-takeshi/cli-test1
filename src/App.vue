<template>
<div>
  <h1></h1>
  <Clock></Clock>
</div>

</template>

<script>
import Clock from './components/Clock.vue'

export default {
  data: function() {
    return {
      counter: 0,
      setImage: [
  require("/images/menu1.jpg"),
  require("/images/menu2.jpg"),
  require("/images/menu3.jpg"),
  require("/images/menu4.jpg")
],
backgroundImage: ''
    }
  },
  methods: {
    slideShow: function() {
      
    }
  },
  components: {
    Clock

  }
}
</script>

<style>
p {
  color: red;
}
</style>
