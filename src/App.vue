<template>
  <div class="app">
    
    <Message :text="loveLetter" />
    <Counter/>
    <Proposal/>
  </div>
</template>

<script>
import Message from './components/Message.vue';
import Counter from './components/Counter.vue';
import Proposal from './components/Proposal.vue';

export default {
  components: {
    Message,
    Counter,
    Proposal
  },
  data() {
    return {
      firstMeeting: "Fast Offer meeting",
      specialDay: "Pratham's house",
      confessionMoment: "your confession",
      tripPlace: "Arai",
      myName: "Your Name", // Replace with your actual name
      loveLetter: ""
    };
  },
  created() {
    this.loveLetter = `
      Do you remember the first time we met? It was at the ${this.firstMeeting}. My first thought when I saw you was, "Who is this girl? She's speaking so well—I need to improve myself to match her!" Later, we met in the garden, where, honestly, I didn't think much about you. But as time went on, I realized you were someone extraordinary—someone I could never quite become. That's when I started admiring you.

      I tried my best to keep up with you, but you were always like a star, shining brightly and just out of my reach. During the presentation competition, I finally fell for you. I was so confused and a little heartbroken because I thought you didn't feel the same way. But despite that, our bond grew stronger with every passing moment.

      The day at ${this.specialDay} remains one of the happiest days of my life. Cohert was unforgettable, too, and I'd love to visit ${this.tripPlace} with you again someday. That trip was magical, but what I cherished most was simply sitting beside you. I still regret not being able to rest on your lap during that time—it would have been so comforting.

      You made my birthday so special with those beautiful cards. And those late-night walks with you and the group? They're some of my favorite memories. Then came ${this.confessionMoment}—it caught me completely off guard! I was so happy that I couldn't even sleep that night.

      Our late-night conversations after that were simply amazing. The more I got to know you, the deeper I fell in love. You are my inspiration, my motivation, and my everything.

      Congratulations on getting placed! I'm so proud of you, and I truly hope all your dreams come true.

      With all my love,  
      ${this.myName}
    `;
  }
};
</script>

<style>
.app {
  display: flex;
  flex-direction: column; /* Stack child components vertically */
  justify-content: center;
  align-items: center;
  min-height: 100vh; /* Ensure it takes at least the full viewport height */
  background: linear-gradient(to bottom, #ffe6e6, #ffccff);
  overflow: hidden; /* Prevent components from spilling outside the container */
  box-sizing: border-box; /* Include padding in size calculations */
  padding: 20px; /* Add some padding to prevent content from touching edges */
}


</style>
