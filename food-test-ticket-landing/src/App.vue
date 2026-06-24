<template>
  <div>

    <HeaderSection :favouriteCount="favouriteCount" />

    <div class="tickets">
      <TicketCard
        v-for="ticket in tickets"
        :key="ticket.id"
        :ticket="ticket"
        @favourite="addFavourite"
      />
    </div>

  </div>
</template>

<script>
import HeaderSection from './components/HeaderSection.vue'
import TicketCard from './components/TicketCard.vue'

export default {
  components: {
    HeaderSection,
    TicketCard
  },

  data() {
    return {
      favouriteCount: 0,
      tickets: [
        {
          id: 1,
          name: "Bronze",
          price: 250,
          description: "Perfect for casual food lovers.",
          benefits: ["General Entry", "Food Stalls", "Live Music"],
          featured: false,
          favourited: false
        },
        {
          id: 2,
          name: "Silver",
          price: 450,
          description: "More perks and comfort.",
          benefits: ["Priority Entry", "Reserved Seating", "Drink Voucher"],
          featured: true,
          favourited: false
        },
        {
          id: 3,
          name: "Gold",
          price: 700,
          description: "VIP full experience.",
          benefits: ["VIP Access", "Chef Meet", "Lounge Access"],
          featured: false,
          favourited: false
        }
      ]
    }
  },

  methods: {
    addFavourite(ticket) {
      if (!ticket.favourited) {
        ticket.favourited = true
        this.favouriteCount++
      }
    }
  }
}
</script>