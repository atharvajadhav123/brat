<template>
  <div class="app">
    
    <Message text="I love you more with every passing day. test one two three four five six seven eight nine ten" />
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
