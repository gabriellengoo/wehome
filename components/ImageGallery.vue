<template>
    <div class="image-gallery-container" @click="changeItem">
      <img :src="currentItem.image" :alt="currentItem.alt" class="responsive-image" />
      <p :class="textPositionClass" class="poptextstyle">
        <span v-if="currentItem.linkType === 'email'">
          <a :href="'mailto:' + currentItem.linkText">{{ currentItem.text }}</a>
        </span>
        <span v-else-if="currentItem.linkType === 'mail'">
          <a :href="'mailto:' + currentItem.linkText">{{ currentItem.text }}</a>
        </span>
        <span v-else-if="currentItem.linkType === 'newsletter'">
          <a :href="currentItem.linkText" target="_blank" rel="noopener noreferrer">{{ currentItem.text }}</a>
        </span>
        <span v-else>
          {{ currentItem.text }}
        </span>
      </p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: [
          // wearethenewhope we are the new hope
          { image: 'https://i.ibb.co/wpW0V4C/Asset-1.png', alt: 'Image 1', text: '', linkType: null, linkText: null },
          { image: 'https://i.ibb.co/khT3YJg/tounge-ezgif-com-svg-to-png-converter.png', alt: 'Image 2', text: 'Email', linkType: 'email', linkText: 'contact@chisaraagor.com' },
          { image: 'https://i.ibb.co/ZVt0nh7/eyebrows-ezgif-com-svg-to-png-converter.png', alt: 'Image 3', text: 'Contact', linkType: 'mail', linkText: 'contact@chisaraagor.com' },
          { image: 'https://i.ibb.co/HzGhRMP/smile-ezgif-com-svg-to-png-converter.png', alt: 'Image 4', text: 'Newsletter', linkType: 'newsletter', linkText: 'https:/wearethenewhope.com' },
          { image: 'https://i.ibb.co/W2P07vC/eyestoright-ezgif-com-svg-to-png-converter.png', alt: 'Image 5', text: 'Site in development', linkType: null, linkText: null },
          // Add more items as needed
        ],
        currentItemIndex: 0,
      };
    },
    computed: {
      currentItem() {
        return this.items[this.currentItemIndex];
      },
      textPositionClass() {
        switch (this.currentItemIndex % 5) {
          case 0:
            return 'text-top';
          case 1:
            return 'text-right';
          case 2:
            return 'text-bottom';
          case 3:
            return 'text-left';
        }
      },
    },
    methods: {
      changeItem() {
        // Increment the index, reset to 0 if it exceeds the array length
        this.currentItemIndex = (this.currentItemIndex + 1) % this.items.length;
      },
    },
  };
  </script>
  
  <style scoped>
  .poptextstyle {
    text-transform: uppercase;
    font-size: 4rem;
    line-height: 3.5rem;
    text-decoration: none;
  color: black;
  animation: bounce .5s infinite alternate;
  }

  @keyframes bounce {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-10px); /* Adjust the bounce height as needed */
  }
}
  
  .image-gallery-container {
    position: relative;
    text-align: center;
    display: flex;
    align-items: center;
    height: 100vh;
  }
  
  .responsive-image {
    max-width: 100%;
    height: auto;
    display: block;
    margin: 0 auto;
    width: 30vw;
  }

  
  .text-top {
    position: absolute;
    top: 0px;
    left: 40%;
    transform: translateX(-40%);
  }
  
  .text-right {
    position: absolute;
    top: 40%;
    right: 10px;
    transform: translateY(-40%);
  }
  
  .text-bottom {
    position: absolute;
    bottom: 5px;
    left: 40% !important;
    transform: translateX(-40%);
  }
  
  .text-left {
    position: absolute;
    top: 40%;
    left: 10px;
    transform: translateY(-40%);
  }

    
  @media (max-width: 768px) {
    .responsive-image {
      width: auto;
    }
  
    .poptextstyle {
      text-transform: uppercase;
      font-size: 2rem;
      line-height: 2rem;
    }

    .text-bottom {
    position: absolute;
    bottom: 5px;
    left: 29% !important;
    transform: translateX(-40%);
  }
  }
  
  /* Add your component-specific styles here */
  </style>
  