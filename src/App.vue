<template>
  <div class="grid-container">
    <div
      v-for="(card, index) in cards"
      :key="index"
      class="card-wrapper"
      :class="{ flipped: card.isFlipped }"
      @click="flipCard(index)"
    >
      <Card class="card front">
        <template #header>
          <h3>{{ card.title }}</h3>
        </template>
      </Card>

      <Card class="card back">
        <template #content>
          <p>{{ card.description }}</p>
        </template>
      </Card>
    </div>
  </div>
</template>

<script>
import Card from 'primevue/card';

export default {
  components: { Card },
  data() {
    return {
      cards: [
        { title: "Memory", description: "King", isFlipped: false },
        { title: "Memory", description: "Queen", isFlipped: false },
        { title: "Memory", description: "Princess", isFlipped: false },
        { title: "Memory", description: "Prince", isFlipped: false },
        { title: "Memory", description: "King", isFlipped: false },
        { title: "Memory", description: "Princess", isFlipped: false },
        { title: "Memory", description: "Prince", isFlipped: false },
        { title: "Memory", description: "Queen", isFlipped: false },
      ]
    };
  },
  methods: {
    flipCard(index) {
      this.cards[index].isFlipped = !this.cards[index].isFlipped;
    }
  }
};
</script>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px;
  justify-items: center;
  margin: 20px;
}

.card-wrapper {
  position: relative;
  width: 150px;
  height: 200px;
  transform-style: preserve-3d;
  transition: transform 0.6s;
}

.card-wrapper.flipped {
  transform: rotateY(180deg);
}

.card {
  width: 100%;
  height: 100%;
  position: absolute;
  backface-visibility: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.front {
  background: black;
  border: 1px solid white;
}

.back {
  background: white;
  color: Red;
  transform: rotateY(180deg);
}
</style>
