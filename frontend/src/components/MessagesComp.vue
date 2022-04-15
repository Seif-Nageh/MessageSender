<template>
  <v-container>
    <v-row>
      <v-col
        class="ma-auto"
        cols="12"
        sm="10"
        md="6"
      >
        <p v-text="messa"></p>
        <v-card class="pa-3">
          <v-toolbar>
            <v-toolbar-title>Messages</v-toolbar-title>
          </v-toolbar>
          <v-list class="ms-3" density="compact">
            <v-list-item v-for="(message, index) in messages" :key="index" :value="message" active-color="primary">
              <v-list-item-title class="text-h5" v-text="message"></v-list-item-title>
            </v-list-item>
          </v-list>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from 'axios';
export default {
  name: 'MessagesComp',

  data: () => ({
    messages: []
  }),
  watch:{
  },
  props:["messa"],
  // emits:["newMessage"],
  async created() {
    this.messages = (await axios.get('http://localhost:3000/messages')).data;
    // this.messages.push(this.messa);
    // console.log(this.messages);
  }
}
</script>
