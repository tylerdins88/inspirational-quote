<template>
  <p class="descrip">An Inspirational Quote to help you ponder.</p>
  <div class="quote">
    <QuoteAPI />
  </div>
  <div class="inverse-wrapper">
    <div class="inverse">Thank You for Visiting.</div>
  </div>
</template>

<script>
import QuoteAPI from "./components/QuoteAPI.vue";

export default {
  name: "App",
  components: {
    QuoteAPI,
  },
};
</script>
