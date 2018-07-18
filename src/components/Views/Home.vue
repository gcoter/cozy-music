<template>
  <div>
    <h1>Songs</h1>
    <div id="players">
      <div class="song-player">
        <img amplitude-song-info="cover_art_url" amplitude-main-song-info="true"/>
        <div class="bottom-container">
          <progress class="amplitude-song-played-progress" amplitude-main-song-played-progress="true" id="song-played-progress"></progress>

          <div class="time-container">
            <span class="current-time">
              <span class="amplitude-current-minutes" amplitude-main-current-minutes="true"></span>:<span class="amplitude-current-seconds" amplitude-main-current-seconds="true"></span>
            </span>
            <span class="duration">
              <span class="amplitude-duration-minutes" amplitude-main-duration-minutes="true"></span>:<span class="amplitude-duration-seconds" amplitude-main-duration-seconds="true"></span>
            </span>
          </div>

          <div class="control-container">
            <div class="amplitude-play-pause" amplitude-main-play-pause="true" id="play-pause"></div>
            <div class="meta-container">
              <span amplitude-song-info="name" amplitude-main-song-info="true" class="song-name"></span>
              <span amplitude-song-info="artist" amplitude-main-song-info="true"></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<link rel="stylesheet" type="text/css" href=""/>

<script>
import Vue from 'vue';
import Amplitude from 'amplitudejs/dist/amplitude.js';

export default {
  mounted: function() {
    Amplitude.init({
      "songs": [
        {
          "name": "Test",
          "artist": "The Testing Guy",
          "album": "Testing Everything",
          "url": "...",
          "cover_art_url": "..."
        }
      ]
    })
  }
}
</script>
