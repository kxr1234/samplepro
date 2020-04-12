<template>
  <v-container>
    <v-card>
      <v-card-text class="text-center">
        <v-form>
          <vue-web-cam ref="webcam" width="100%" :device-id="deviceId" @cameras="onCameras" />

          <v-switch
            v-model="switchVideo"
            :label="`Video: ${switchVideo.toString()}`"
            @change="onStart"
          ></v-switch>
        </v-form>
      </v-card-text>
    </v-card>
  </v-container>
</template> 

<script>
import { WebCam } from "vue-web-cam";

export default {
  name: "Video",

  components: {
    "vue-web-cam": WebCam
  },

  data: () => ({
    switchVideo: true,

    img: null,

    camera: null,

    deviceId: null,

    devices: []
  }),

  computed: {
    device: function() {
      return this.devices.find(n => n.deviceId === this.deviceId);
    }
  },

  watch: {
    camera: function(id) {
      this.deviceId = id;
    },

    devices: function() {
      // Once we have a list select the first one

      const [first] = this.devices;

      if (first) {
        this.camera = first.deviceId;

        this.deviceId = first.deviceId;
      }
    },
    switchVideo(value) {
      value === true ? this.$refs.webcam.start() : this.$refs.webcam.stop();
    }
  },

  methods: {
    onCameras(cameras) {
      this.devices = cameras;
    }
  }
};
</script> 

 
 

 