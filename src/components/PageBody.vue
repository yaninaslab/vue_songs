<template>
    <div>
        <h1>Welcome to My Music Collection</h1>
        <button @click="add_song">Add Song</button>
        <song-list :songs="songs" @select_song="add_that_song"></song-list>
        <play-list :songs="selected_songs"></play-list>
    </div>
</template>

<script>
import SongList from './SongList.vue'
import PlayList from './PlayList.vue'

    export default {
        name: "page-body",
        components: {
            SongList,
            PlayList,
        
        },
        methods: {
            add_song() {
                // var songs_length = this.selected_songs.length;
                var unselected_songs = this.songs.filter(
                    (song) => {
                        return this.selected_songs.findIndex(
                            (item) => item.id === song.id
                        ) === -1;
                    }
                );

                var new_song = unselected_songs[0];

                if(new_song) {
                    this.selected_songs.push(new_song);
                }else {
                    alert("All songs have been added!")
                }
            },
            add_that_song(id) {
                var that_song = this.songs.find((song) => song.id === id); // song object || null

                if (that_song) {
                    var isSelected = this.selected_songs.findIndex((song) => song.id === id) >= 0;

                    if (isSelected) {
                        alert('Song is already in the playlist!')
                    } else {
                        this.selected_songs.push(that_song);
                    }
                }
            }
        },
         data() {
            return {
                selected_songs: [
                    {id: 1, title: 'My Way', artist: 'Cassette'},
                ],
                songs: [
                    {id: 1, title: 'My Way', artist: 'Cassette'},
                    {id: 2, title: 'Love', artist: 'Lena'},
                    {id: 3, title: 'In Your Eyes', artist: 'The Weeknd'},
                    {id: 4, title: 'Out of Time', artist: 'Why So Sad'},
                    {id: 5, title: 'So Long', artist: 'MALFA'},
                    {id: 6, title: "Test", artist: "Test123"}
                ]
            }
        },
    
    }
</script>

<style scoped>

</style>