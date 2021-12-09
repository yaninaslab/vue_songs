<template>
<div>
    <h2 class="playlist">Song Collection</h2>
    <h2 v-for="song in songs" :key="song.id">{{ song.id }}
         {{ song.title }}
          {{ song.artist }}</h2>
    
    <play-list @song_added="react_to_song_added">

    </play-list>
   <h2>{{ song_added }}</h2>
    </div>
</template>

<script>
import PlayList from './PlayList.vue'

    export default {
        name: "song-list",
        components: {
            PlayList,
        },
        methods: {
            react_to_song_added(playload) {
                this.song_added = playload;
            }
        },
        data() {
            return {
                song_added: undefined,
                songs: [
                    {id: 1, title: 'My Way', artist: 'Cassette'},
                    {id: 2, title: 'Love', artist: 'Lena'},
                    {id: 3, title: 'In Your Eyes', artist: 'The Weeknd'},
                    {id: 4, title: 'Out of Time', artist: 'Why So Sad'},
                    {id: 5, title: 'So Long', artist: 'MALFA'},
                ]
            }
        },
        props: {
           id: Number,
           title: String,
           artist: String
        },
    }
</script>

<style scoped>
.playlist {
    color: blue;
    margin-top: 50px;
    text-align: center;
}
</style>