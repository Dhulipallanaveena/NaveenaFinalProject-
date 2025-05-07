<template>
  <!-- Step 3: use the component -->
  <MyHeader :bookName="phoneName" :authorName="companyName" />
  <BookBox :books="mobile" />
</template>

<script>
// Step 1: import the component
import MyHeader from './components/MyHeader.vue'
import BookBox from './components/BookBox.vue';

export default {
  name: 'App',

  // Step 2: register the component
  components: {
    MyHeader,
    BookBox
  },
  data() {
    return {
      mobile: [],
      
    }
  },
  methods: {
    // Use promises to fetch mobile data
    async fetchmobiles() {
      const res = await fetch("http://localhost:9259/mobile");
      const data = await res.json();
      console.log(data);
      return data;
    }
  },
  async created() {
    this.mobile = await this.fetchmobiles();

    // Set phone name and company name based on the first phone in the list
    if (this.mobile && this.mobile.length > 0) {
      this.phoneName = "Animes";
      this.companyName = "phones";
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}

.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div {
  margin-bottom: 0.5em;
  text-align: center;
}
</style>
