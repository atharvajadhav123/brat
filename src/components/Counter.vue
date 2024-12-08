<template>
    <div class="countdown-container">
      <div class="countdown">
        <div class="time-unit">
          <span class="time-value">{{ days }}</span>
          <span class="time-label">Days</span>
        </div>
        <div class="time-unit">
          <span class="time-value">{{ hours }}</span>
          <span class="time-label">Hours</span>
        </div>
        <div class="time-unit">
          <span class="time-value">{{ minutes }}</span>
          <span class="time-label">Minutes</span>
        </div>
        <div class="time-unit">
          <span class="time-value">{{ seconds }}</span>
          <span class="time-label">Seconds</span>
        </div>
      </div>
    </div>
    <div class="message">
        Number of days since you Confessed me.
    </div>
    
  </template>
  
  <script>
  export default {
    data() {
      return {
        startTime: new Date('2024-07-28T23:55:00'), // Start time of the timer (current time)
        days: 0,
        hours: 0,
        minutes: 0,
        seconds: 0,
      };
    },
    mounted() {
      this.updateTimer();
      setInterval(this.updateTimer, 1000); // Update every second
    },
    methods: {
      updateTimer() {
        const now = new Date();
        const elapsed = now - this.startTime;
  
        this.days = Math.floor(elapsed / (1000 * 60 * 60 * 24));
        this.hours = Math.floor((elapsed % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        this.minutes = Math.floor((elapsed % (1000 * 60 * 60)) / (1000 * 60));
        this.seconds = Math.floor((elapsed % (1000 * 60)) / 1000);
      },
    },
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&display=swap');
  
  .countdown-container {
    text-align: center;
    padding: 20px;
    font-family: 'Dancing Script', cursive; /* Romantic font */
    color: #ff6f91; /* Romantic pink color */
    background-color: #f9e4e9; /* Soft pink background */
    border-radius: 10px;
    width: 300px;
    margin: 20px auto;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  }
  
  .countdown {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
  }
  
  .time-unit {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .time-value {
    font-size: 40px;
    font-weight: bold;
    color: #e6b0b0; /* Soft red */
    margin-bottom: 5px;
  }
  
  .time-label {
    font-size: 14px;
    color: #d07474; /* Lighter pink */
  }
  .message{ 
    font-size: 24px;
    color: #ff6f91; /* Romantic pink */
    display: inline-block;
    overflow: hidden;
    position: relative;
    font-weight: 700;
    padding: 30px;
    padding-bottom: 100px;
  }
  ::-webkit-scrollbar {
  width: 10px; /* Width of the scrollbar */
}

::-webkit-scrollbar-thumb {
  background: #ff69b4; /* Pink color for the scrollbar thumb */
  border-radius: 5px; /* Rounded scrollbar edges */
}

::-webkit-scrollbar-thumb:hover {
  background: #ff1493; /* Darker pink on hover */
}

::-webkit-scrollbar-track {
  background: #ffe6e6; /* Light pink for the track */
}
  </style>
  