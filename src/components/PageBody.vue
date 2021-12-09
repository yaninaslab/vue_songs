<template>
    <div>
        <h1>Welcome to My Music Collection</h1>
<song-list>

    <h2 v-for="song in songs" :key="song.id"
    :title="song.title"
    :artist="song.artist"
    >
        {{ song.id }} {{ song.title }} {{ song.artist }}</h2>
</song-list>
    </div>
</template>

<script>
import SongList from './SongList.vue'

    export default {
        name: "page-body",
        components: {
            SongList,
        
        },
        data() {
            return {
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

</style>