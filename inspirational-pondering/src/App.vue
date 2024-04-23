<template>
  <p class="descrip">An Inspirational Quote to help you ponder.</p>
  <div>
    <QuoteAPI />
  </div>
  <div class="inverse">Thank You for Visiting.</div>
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
