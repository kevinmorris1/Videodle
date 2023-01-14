<script>
export default {
  name: "Video",
  data() {
    return {
      player: null,
      duration: 1000,
    };
  },
  methods: {
    YouTubeIframeAPIReady: function () {
      this.player = new YT.Player("player", {
        height: "390",
        width: "640",
        videoId: "IvlasC9nvu8",
        playerVars: {
          playsinline: 1,
        },
        events: {
          onReady: this.onPlayerReady,
          onStateChange: this.onPlayerStateChange,
        },
      });
    },
    onPlayerReady: function () {
      this.player.playVideo();
    },
    onPlayerStateChange: function (event) {
      if (event.data == YT.PlayerState.PLAYING) {
        setTimeout(this.stopVideo, this.duration);
      }
    },
    stopVideo: function () {
      this.player.stopVideo();
    },
  },
  beforeMount() {},
  mounted() {
    var tag = document.createElement("script");

    tag.src = "https://www.youtube.com/iframe_api";
    var firstScriptTag = document.getElementsByTagName("script")[0];
    firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

    setTimeout(this.YouTubeIframeAPIReady, 1000);
  },
};
</script>

<template>
  <div id="player"></div>
  <button
    @click="
      () => {
        this.player.playVideo();
        this.duration = this.duration + 5000;
      }
    "
  >
    Play
  </button>
</template>

<style>
#player {
  width: 100%;
  height: 50%;
}
</style>
