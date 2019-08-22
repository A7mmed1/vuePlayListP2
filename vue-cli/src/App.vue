<template>
  <div id="app">
      <play-list v-on:favoriteSong="favoriteSong"  v-on:deleteSongEvent="deleteSong">     </play-list>


  </div>
</template>

<script>
import  PlayList from './components/PlayList.vue'
export default {

  name: 'app',
  components: {
      PlayList



  },

  methods: {
      favoriteSong(song){
          song.fav = ! song.fav
      },
      deleteSong(index){
          

      }
  }
}
</script>

<style lang="scss">

.favorite{
    background-color: green;
}

</style>
