<template>
  <div class="card" :class="{ featured: ticket.featured }">

    <div v-if="ticket.featured" class="badge">
      Featured
    </div>

    <h2>{{ ticket.name }}</h2>
    <h3>R{{ ticket.price }}</h3>

    <p>{{ ticket.description }}</p>

    <ul>
      <li v-for="b in ticket.benefits" :key="b">
        {{ b }}
      </li>
    </ul>

    <button @click="$emit('favourite', ticket)" :disabled="ticket.favourited">
      {{ ticket.favourited ? "❤️ Added" : "🤍 Favourite" }}
    </button>

  </div>
</template>

<script>
export default {
  props: ['ticket']
}
</script>

<style>
.card {
  background: white;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.2);
  position: relative;
}

.card h2 {
  color: #d62828;
}

.card h3 {
  color: #f77f00;
}

button {
  width: 100%;
  padding: 12px;
  border: none;
  background: #f77f00;
  color: white;
  border-radius: 8px;
  cursor: pointer;
}

button:disabled {
  background: gray;
}

.featured {
  border: 3px solid gold;
  transform: scale(1.03);
}

.badge {
  position: absolute;
  top: 10px;
  right: 10px;
  background: gold;
  padding: 5px 10px;
  border-radius: 15px;
  font-weight: bold;
}
</style>