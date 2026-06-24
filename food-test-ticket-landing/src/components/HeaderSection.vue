<template>
  <header class="header">
    <h1>🍔 Cape Town Food Fest 2026</h1>
    <p>Food, music & unforgettable weekend vibes.</p>

    <div class="fav">
      ❤️ Favourite Tickets: {{ favouriteCount }}
    </div>
  </header>
</template>

<script>
export default {
  props: ['favouriteCount']
}
</script>

<style>
.header {
  background: #d62828;
  color: white;
  text-align: center;
  padding: 40px 20px;
}

.fav {
  margin-top: 15px;
  font-weight: bold;
}
</style>