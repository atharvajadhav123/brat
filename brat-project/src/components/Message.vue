<template>
    <div class="message-container">
      <!-- Import PNG Ribbon with animation -->
      <img class="ribbon" src="../assets/ribbon.png" alt="Ribbon" />
      <div class="message">
        <span
          v-for="(word, index) in words"
          :key="index"
          class="word"
          :style="{ animationDelay: `${index * 0.5}s` }"
        >
          {{ word }}
        </span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      text: {
        type: String,
        required: true,
      },
    },
    computed: {
      words() {
        return this.text.split(' '); // Split the message into words
      },
    },
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&display=swap');
  
  .message-container {
    text-align: center;
    position: relative;
    margin-top: 50px;
  }
  
  .ribbon {
    width: 110px; /* Adjust the size as per your PNG */
    height: auto;
    position: absolute;
    top: -67px; /* Position the ribbon above the text */
    left: 50%;
    transform: translateX(-50%);
    opacity: 0; /* Initially invisible */
    animation: ribbon-fade-in 1s ease forwards;
  }
  
  .message {
    font-family: 'Dancing Script', cursive;
    font-size: 24px;
    color: #ff6f91; /* Romantic pink */
    display: inline-block;
    overflow: hidden;
    position: relative;
    padding-top: 50px; /* Add space for ribbon */
  }
  
  .word {
    display: inline-block;
    margin-right: 5px;
    opacity: 0;
    transform: translateY(10px);
    animation: appear 0.5s ease-out forwards;
  }
  
  @keyframes appear {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  @keyframes ribbon-fade-in {
    0% {
      opacity: 0;
      transform: translateX(-50%) scale(0.8);
    }
    100% {
      opacity: 1;
      transform: translateX(-50%) scale(1);
    }
  }
  </style>
  