<template>
    <div>
      <h2>Vinyllijst</h2>
      <ul v-if="albums.length">
        <li v-for="album in albums" :key="album.id"></li>
      </ul>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    name: 'vinylList',
    data() {
      return {
        albums: []
      };
    },
    created() {
      this.fetchAlbums();
    },
    methods: {
      fetchAlbums() {

      }
    }
  };
  </script>
  