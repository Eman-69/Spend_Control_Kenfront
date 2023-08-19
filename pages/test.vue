<template>
    <div class="main-background">
      <div class="animation"><Animationtest :scrollPer="scrollPer" /></div>
      <!-- <div class="nav"><Navbar /></div> -->
      <div class="container" ref="el" @scroll="handleScroll()">
        <div id="id1"><Slide1 /></div>
        <div id="id2" ><Slide3 /></div>
        <div id="id2"><Slide4 /></div>
        <div id="id2"><Slide5 /></div>
        <div id="id2" ><Slide2/></div>
        <div id="id2" ><Slide2 /></div>
        <div id="id2" ><Slide2 /></div>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  const el = ref(null);
  let scrollPer = ref(0);
  
  const handleScroll = () => {
    const scrollTop = el.value.scrollTop;
    const scrollHeight = el.value.scrollHeight;
    const clientHeight = el.value.clientHeight;
    scrollPer.value = (scrollTop / (scrollHeight - clientHeight)) * 100;
  
    // Increase the scroll time by 2 seconds (2000 milliseconds)
    el.value.style.scrollBehavior = "smooth";
    el.value.style.scrollDuration = "2000";
    console.log(el.value.style);
  };
  </script>
  
  <style scoped>
  .animation {
    position: absolute;
    height: 100vh;
    width: 100vw;
    z-index: -1;
  }
  .container {
    overflow-y: scroll;
    height: 100vh;
    scroll-behavior: smooth;
  }
  .container > div {
    height: 100vh;
  }
  </style>
  