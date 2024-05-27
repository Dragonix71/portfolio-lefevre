<!-- src/components/BackToTop.vue -->
<template>
    <button class="back-to-top" :class="{ show: isVisible }" @click="scrollToTop">↑ Back to Top</button>
  </template>
  
  <script>
  export default {
    name: 'BackToTop',
    data() {
      return {
        isVisible: false
      };
    },
    methods: {
      scrollToTop() {
        window.scrollTo({ top: 0, behavior: 'smooth' });
      },
      handleScroll() {
        this.isVisible = window.scrollY > 50;
      }
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll);
    },
    beforeUnmount() {
      window.removeEventListener('scroll', this.handleScroll);
    }
  };
  </script>
  
  <style scoped>
  .back-to-top {
    position: fixed;
    bottom: 20px;
    right: 20px;
    opacity: 0;
    transition: opacity 0.3s;
    background-color: #333;
    color: white;
    border: none;
    padding: 10px 20px;
    cursor: pointer;
    border-radius: 5px;
  }
  
  .back-to-top.show {
    opacity: 1;
  }
  
  .back-to-top:hover {
    background-color: #555;
  }
  </style>
  