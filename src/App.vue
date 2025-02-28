<template>
  <div class="gallery-container">
    <header class="gallery-header">
      <h1>Artistic Visions Gallery</h1>
    </header>
    <main class="gallery-grid">
      <div v-for="art in artworks" :key="art.id" class="gallery-item">
        <img :src="art.image" :alt="art.title" class="art-image" />
        <h2 class="art-title">{{ art.title }}</h2>
        <p class="art-artist">by {{ art.artist }}</p>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      artworks: [
        { id: 1, title: "Plankton", artist: "Unknown", image: "/Image.jpg" },
        { id: 2, title: "Moth", artist: "Emily Smith", image: "/Image 4.jpg" },
        { id: 3, title: "Colorful Vision", artist: "Anonymous", image: "/Image 5.jpg" },
        { id: 4, title: "Golden Praise", artist: "H. Miyazaki", image: "/Image 6.jpg" }
      ]
    };
  }
};
</script>

<style scoped>
.gallery-container {
  text-align: center;
  padding: 20px;
}

.gallery-header {
  background-color: #222;
  color: white;
  padding: 10px;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin-top: 20px;
}

.gallery-item {
  border: 1px solid #ddd;
  padding: 10px;
  border-radius: 8px;
  background: white;
}

.art-image {
  max-width: 100%;
  border-radius: 8px;
}

.art-title {
  color: aqua;
  margin: 10px 0 5px;
  font-size: 1.2em;
}

.art-artist {
  color: #555;
  font-style: italic;
}
</style>
