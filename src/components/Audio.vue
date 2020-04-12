<template>
  <v-container width="700" class="mx-auto">
    <v-row align="center">
      <v-col cols="3">
        <v-subheader>Output source</v-subheader>
      </v-col>

      <v-col cols="3">
        <av-line :line-width="2" line-color="lime" audio-src="testAu.mp3"></av-line>
      </v-col>
    </v-row>

    <v-row>
      <v-col cols="3">
        <v-subheader>Input Source</v-subheader>
      </v-col>

      <v-col cols="3">
        <audio ref="player"></audio>

        <av-media type="frequ" :media="media" line-color="darkorange" />
      </v-col>
    </v-row>
  </v-container>
</template> 

 
 

<script>
export default {
  name: "Audio",

  data: () => ({
    inputSources: ["Mike1", "Mike2"],

    outputSources: ["speaker", "Headset"],

    mtype: null,

    media: null
  }),

  mounted() {
    const audio = this.$refs.player;

    const constraints = {
      audio: true,

      video: false
    };

    navigator.mediaDevices.getUserMedia(constraints).then(media => {
      this.media = media;

      audio.srcObject = media;
    });
  }
};
</script> 

 