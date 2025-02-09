<!-- app.vue -->
<template>
  <div id="app">
    <div class="container container--heading">
      <h2 class="heading__title">De nieuwste LP's</h2>
      <a class="heading__link" href="#">Bekijk alle nieuwe LP's ></a>
    </div>
    <div class="container">
      <div v-if="albums.length">
        <ul class="albums">
          <single-album 
            v-for="album in albums.slice(0, 5)" 
            :key="album.id"
            :title="album.title"
            :year="album.year"
            :genre="album.genre"
            :cover-image="album.cover_image"
          />
        </ul>
      </div>
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
    gap: 1.5rem;
    max-width: 1400px;
  }

  .heading__title {
    margin-right: 1rem;
    color: #DF8032;
  }

  .heading__link {
    font-size: .9rem;
    text-decoration: none;
    margin: 0;
    font-weight: 200;
    margin-bottom: .2rem;
  }
</style>
