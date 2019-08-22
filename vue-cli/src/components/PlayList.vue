<template >
    <ul class="playlist">
        <song :class="song.fav ? 'favorite' : ''"  v-for= "(song,index) in songs"
        :key="index"
        :artist="song.artist"
        :title="song.title">
            <br >{{song.artist}} - {{song.title}}
            <button  class="btn btn-warning"@click.prevent="favoriteSong(song)" type="button"> Fav</button>
            <button class="btn btn-danger"@click.prevent="deleteSong(index)" type="button">Delete</button>


        </song>
    </ul>

</template>

<script>
import Song from './Song.vue'
export default {




    name: 'playList',

    components: {
        Song
    },
    methods:{
        favoriteSong(song){
            this.$emit("favoriteSong",song)

        },
        deleteSong(index){
            alert(index);
            console.log("delete" + index);
            this.songs.splice(index,1);        }

    },


    data() {
        return {
            songs: [
                {id:1 ,fav:false , artist:'ahmmed', title:'wtf'},
                {id:2 , fav:false ,artist:'seal', title:'Kiss from a Rose'},
                {id:3 , fav:false ,artist:'seal', title:'Kiss from a Rose'},


            ]
        }


    }
}
</script>

<style lang="scss" >

.playList{
    width: 25%;
}
.favorite{
    background-color: green;
    width: 25% ;
}
</style>
