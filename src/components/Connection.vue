<template>
  <v-app width="1000" class="mx-auto">
    <v-card>
      <v-card-text>
        <p>Connected Status = {{connectionStatus}}</p>
      </v-card-text>

      <v-card-actions>
        <v-btn @click="myFunction()">Check connection</v-btn>

        <v-btn @click="resetFunction()">Reset connection</v-btn>
      </v-card-actions>
    </v-card>
  </v-app>
</template> 

 
 

<script>
export default {
  name: "Connection",

  data: () => ({
    connectionStatus: ""
  }),

  methods: {
    myFunction: function() {
      if (navigator.onLine) {
        this.connectionStatus = "Connected to internet.";
      } else {
        this.connectionStatus = "Unable to connect to internet.";
      }
    },
    resetFunction: function() {
      this.connectionStatus = "";
    }
  }
};
</script> 

 
 

 