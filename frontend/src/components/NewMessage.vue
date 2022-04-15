<template>
    <v-container>
      <v-row>
        <v-col
          class="ma-auto"
          cols="12"
          sm="8"
          md="4"
        >
        <v-card>
          <v-toolbar>
            <v-toolbar-title>New Message</v-toolbar-title>
          </v-toolbar>
        <v-form>
          <v-text-field
            class="pa-4"
            v-model="newMessage"
            required
            variant="underlined"
            label="New Message"
          ></v-text-field>
          <v-btn class="mx-5 mb-3" variant="text" @click="submit">Send Message</v-btn>
        </v-form>
        </v-card>
        </v-col>
      </v-row>
    </v-container>
</template>

<script>
import axios from 'axios';
export default {

  data: () => ({
    newMessage: ""
  }),
  methods: {
    submit(){
      axios.post('http://localhost:3000/messages', {message : this.newMessage});
      this.$emit("newMessage", this.newMessage);
    }
  }
}
</script>
