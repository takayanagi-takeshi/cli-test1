<template>
<div id="bg-img" v-bind:style="{'background-image': backgroundImage}">
  <Clock></Clock>
</div>

</template>

<script>
import Clock from './components/Clock.vue';

export default {
  data: function() {
    return {
      counter: 0,
      setImage: [
        require("@/assets/images/menu1.jpg"),
        require("@/assets/images/menu2.jpg"),
        require("@/assets/images/menu3.jpg"),
        require("@/assets/images/menu4.jpg")
      ],
      backgroundImage: ''
    }
  },
    components: {
      Clock
  },
  created: function() {
    let that = this;
    setInterval(that.slideShow,5000)
  },
  methods: {
    slideShow: function() {
      if(this.counter > this.setImage.length-1) {
        this.counter = 0;
      }
      this.backgroundImage = `url(${this.setImage[this.counter]})`;
      this.counter++
    }
  },
}

</script>

<style>
#bg-img {
  width: 100vh;
  height: 100vh;
  background-image: url(./assets/images/menu1.jpg);
  background-size: cover;
  background-position: top center;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 3.5s ease;
}
</style>
