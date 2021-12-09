<template>
    <div>
        <h2 class="playlist">My Playlist</h2>
        <button @click="add_song" ref="btn">Add Song</button>
    </div>
</template>

<script>
    export default {
        name: "play-list",
        methods: {
            add_song() {
                this.$emit('song_added', "Song added to the playlist");
                this.$refs['btn'].style.background = "lightblue";
            },
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