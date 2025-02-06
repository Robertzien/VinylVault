<template>
  <div id="app">
    <h1>Vinyl Collectie</h1>
    <div v-if="albums.length">
      <ul class="albums">
        <li v-for="album in albums" :key="album.id">
          <img class="album__image" :src="album.cover_image" alt="">
          <h3 class="album__title">{{ album.title }}</h3>
          <p class="album__artist">{{ album.artist }}</p>
        </li>
      </ul>
    </div>
    <p v-else>Loading...</p> 
  </div>
</template>

<script>
import axios from 'axios'; 

export default {
  data() {
    return {
      albums: []  
    };
  },
  created() {
    this.fetchAlbums(); 
  },
  methods: {
    async fetchAlbums() {
      try {
        const response = await axios.get('https://api.discogs.com/database/search', {
          params: {
            q: 'LP', 
            type: 'release',
            token: 'FbAevpWuLulcMOJpLqTmUMPGyQngGwxLlIRPZVfN',  
          }
        });
        this.albums = response.data.results;  
      } catch (error) {
        console.error('Fout bij het ophalen van data:', error); 
      }
    }
  }
};
</script>

<style>
  .albums {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
  }

  .album__image {
    width: 225px;
    height: 225px;
    margin-bottom: 0;
  }
</style>