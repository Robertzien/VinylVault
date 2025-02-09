<!-- app.vue -->
<template>
  <div id="app">
    <div class="container container--heading">
      <h1>Vinyl Collectie</h1>
    </div>
    <div v-if="albums.length">
      <ul class="albums">
        <single-album 
          v-for="album in albums" 
          :key="album.id"
          :title="album.title"
          :year="album.year"
          :cover-image="album.cover_image"
        />
      </ul>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import SingleAlbum from './components/singleAlbum.vue';

export default {
  components: {
    SingleAlbum
  },
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
    grid-template-columns: repeat(5, minmax(150px, 1fr));
    padding: 0;
    margin: 0 auto;
    gap: 1rem;
    max-width: 1400px;
  }
</style>
