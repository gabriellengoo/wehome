<template>
  <div>
    <!-- <marquee class="marquee" behavior="scroll" direction="left" scrollamount="5">Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon</marquee> -->
    <!-- <div class="marquee"><span>Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon  ✴︎   Coming Soon</span></div> -->
    <ImageGallery />
  </div>
</template>

<script>
import ImageGallery from '~/components/ImageGallery.vue';

export default {
  name: 'IndexPage',
  components: {
    ImageGallery,
  },
};
</script>

<style scoped>
.coming-soon {
  font-size: 15px;
  color: black; /* Adjust the color as needed */
  text-align: center;
  padding: 10px;
  position: absolute;
  /* position: absolute;
  left: -50vw; */
  white-space: nowrap;
}

.marquee {
    white-space: nowrap;
    /* position: absolute; */
    /* top: 5vh; */
    font-family: Old Standard TT,serif;
    font-style: italic;
    z-index: 1000
}

.marquee span {
  position: absolute;
    /* display: inline-block; */
    margin-left: 0;
    animation: marquee 100s linear infinite
}

@keyframes marquee {
    0% {
        transform: translate(0)
    }

    to {
        transform: translate(-100%)
    }
}
</style>
