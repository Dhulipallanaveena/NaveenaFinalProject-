<template>
  <div :class="getRatingClass(phone.Rating)" class="phone-card">
    <h2>{{ phone.Name }}</h2>
    <p><strong>Brand:</strong> {{ phone.Company }}</p>
    <p><strong>Released:</strong> {{ phone.Release_Year }}</p>
    <p><strong>Price:</strong> {{ phone.Price }}</p>
    <p><strong>Rating:</strong> {{ phone.Rating }}</p>
    <p><strong>Positive:</strong> {{ phone.Positive }}</p>
    <p><strong>Negative:</strong> {{ phone.Negative }}</p>
    <p><strong>Review:</strong> {{ phone.Reviews }}</p>
  </div>
</template>

<script>
export default {
  name: 'SingleBook',
  props: {
    phone: Object
  },
  methods: {
    getRatingClass(rating) {
      
      const ratingNumber = parseFloat(rating);
      return ratingNumber >= 7 ? 'green' : 'red';
    }
  }
}
</script>

<style scoped>
.green {
  background-color: green;
  color: white;
}

.red {
  background-color: orangered;
  color: white;
}

.phone-card {
  background-color: #ffb89e;
  padding: 1em;
  text-align: center;
  width: 80%;
  margin: 1em auto;
  border-radius: 5px;
}
</style>
