<template>
<div>
    <h2 class="playlist">Song Collection</h2>
    <h2
        v-for="song in songs"
        :key="song.id"
        @click="$emit('select_song', song.id)"
    >
        {{ song.title }}
        {{ song.artist }}
    </h2>
    </div>
</template>

<script>

    export default {
        name: "song-list",

       props: {
           songs: Array,

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