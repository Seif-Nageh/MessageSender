<template>
  <v-app>
    <v-app-bar color="teal-darken-4">
    </v-app-bar>
    <v-main class="bg-main">
      <NewMessage @newMessage="print($event)" />
      <MessagesComp :messa="messa" />

    </v-main>
  </v-app>
</template>

<script>
import MessagesComp from './components/MessagesComp.vue'
import NewMessage from './components/NewMessage.vue'


export default {
  name: 'App',

  components: {
    MessagesComp,
    NewMessage
  },

  data: () => ({
    messa: ""
  }),
  methods:{
    print(mess){
      this.messa = mess;
    }
  }
}
</script>

<style>
.bg-main{
  background-color:#EFEFEF;
}
</style>
