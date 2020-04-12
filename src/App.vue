<template>
  <v-app>
    <v-card width="900" class="mx-auto">
      <v-card-title>
        <v-tabs fixed-tabs background-color="indigo" dark>
          <v-tab>Audio</v-tab>

          <v-tab>Video</v-tab>

          <v-tab-item>
            <Audio></Audio>
          </v-tab-item>

          <v-tab-item>
            <Video></Video>
          </v-tab-item>
        </v-tabs>
      </v-card-title>

      <v-card-text>
        <v-textarea
          name="inputText"
          value=" 

Make sure you are using the device and network that you will be using at the time of your visit. 
For the best possible visit experience ensure you have a strong internet or cellular service connection. Public Wi-Fi connections are not recommended."
          disabled="true"
        ></v-textarea>
      </v-card-text>

      <v-card-actions>
        <Connection></Connection>
      </v-card-actions>
    </v-card>
  </v-app>
</template>

<script>
import Audio from "./components/Audio";

import Video from "./components/Video";

import Connection from "./components/Connection";

export default {
  name: "App",

  components: {
    Audio,

    Video,

    Connection
  },

  data: () => ({
    //
  })
};
</script>
