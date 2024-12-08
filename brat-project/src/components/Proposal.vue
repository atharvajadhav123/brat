<template>
    <div class="proposal">
      <div v-if="stage <= 3 && stage !=0">
        <img :src="currentYesImage" alt="Current Stage Image" class="stage-image" />
        <p class="question">{{ currentQuestion }}</p>
        <button class="btn yes-btn" @click="nextStage('yes')">Yes</button>
        <button class="btn no-btn" @click="nextStage('no')">No</button>
      </div>
  
      <div v-if="stage === 0">
        <img :src="noImage" alt="No Image" class="response-image" />
        <p class="response">I'm sad to hear that. 😔</p>
      </div>
  
      <div v-if="stage === 4">
        <img :src="finalYesImage" alt="Final Yes Image" class="response-image" />
        <p class="response love-message">I love you soooooooooooo much! ❤️</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        stage: 1, // Current question stage
        yesImages: [
          new URL('../assets/Stage1.gif', import.meta.url).href, // Stage 1
          new URL('../assets/Stage2.gif', import.meta.url).href, // Stage 2
          new URL('../assets/Stage3.gif', import.meta.url).href, // Stage 3
          new URL('../assets/Stage4.gif', import.meta.url).href, // Stage 4
        ],
        noImage: new URL('../assets/No-Image.png', import.meta.url).href, // Common GIF for "No"
        questions: [
          'Do you Like me?',
          'I may not be your ideal man, but do you still like me?',
          'For real???????????',
        ],
      };
    },
    computed: {
      currentYesImage() {
        return this.yesImages[this.stage - 1]; // Get image based on the current stage
      },
      currentQuestion() {
        return this.questions[this.stage - 1]; // Get question based on the current stage
      },
      finalYesImage() {
        return this.yesImages[3]; // The final "Yes" image
      },
    },
    methods: {
      nextStage(response) {
        if (response === 'yes') {
          if (this.stage < 4) {
            this.stage += 1; // Move to the next stage
          } else {
            this.stage = 5; // Show the final response
          }
        } else {
          this.stage = 0; // Show the "No" response
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .proposal {
    text-align: center;
    font-family: 'Georgia', serif;
    color: #ff69b4;
    background: linear-gradient(135deg, #ffe4e1, #ffb6c1);
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    max-width: 600px;
    margin: 20px auto;
    max-height: 100vh;
  }
  
  .stage-image {
    width: 300px;
    height: auto;
    margin-bottom: 20px;
    animation: fadeIn 1s ease-in-out;
    border-radius: 10px;
    border: 4px solid #ff1493;
  }
  
  .response-image {
    width: 300px;
    height: auto;
    animation: bounce 1.5s infinite;
    border-radius: 10px;
    border: 4px solid #db7093;
  }
  
  .question {
    font-size: 2em;
    margin-bottom: 20px;
    background-color: rgba(255, 182, 193, 0.8);
    padding: 15px;
    border-radius: 15px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }
  
  .btn {
    padding: 15px 30px;
    font-size: 1.2em;
    margin: 15px;
    border: none;
    border-radius: 50%;
    cursor: pointer;
    transition: transform 0.3s ease-in-out, background-color 0.3s ease-in-out;
    display: inline-block;
    width: 70px;
    height: 70px;
    line-height: 40px;
    color: white;
    text-align: center;
  }
  
  .yes-btn {
    background-color: #ff69b4;
    box-shadow: 0 4px 8px rgba(255, 105, 180, 0.4);
  }
  
  .no-btn {
    background-color: #ff4500;
    box-shadow: 0 4px 8px rgba(255, 69, 0, 0.4);
  }
  
  .btn:hover {
    transform: scale(1.2);
  }
  .love-message {
  font-size: 2em; /* Adjust font size as needed */
  font-weight: bold; /* Make the text bold */
  color: #ff69b4; /* Romantic pink color */
  text-align: center;
  margin: 20px 0; /* Add spacing around the message */

  animation: fadeInScale 1.5s ease-in-out;
}
  
  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  
  @keyframes bounce {
    0%, 100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-10px);
    }
  }
  </style>
  