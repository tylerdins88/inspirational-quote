<template>
  <div>
    <h2>{{ quote }}</h2>
    <p>- {{ author }}</p>
    <button @click="fetchNewQuote">Get New Quote</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "QuoteAPI",
  data() {
    return {
      quote: "",
      author: "",
    };
  },
  methods: {
    async fetchNewQuote() {
      try {
        const response = await axios.get(
          "https://quotes15.p.rapidapi.com/quotes/random/",
          {
            headers: {
              "X-RapidAPI-Key":
                "2b148a14a3msh12fa6ec54fe1b3fp1ed456jsnbd039561a19d",
              "X-RapidAPI-Host": "quotes15.p.rapidapi.com",
            },
          }
        );
        this.quote = response.data.content;
        this.author = response.data.originator.name;
      } catch (error) {
        console.error("Error fetching quote:", error);
        this.quote = "Failed to fetch a quote. Please try again later.";
        this.author = "Unknown";
      }
    },
  },
  created() {
    this.fetchNewQuote(); // Fetch quote on component creation
  },
};
</script>
