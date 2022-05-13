<template>
  <v-sheet class="pa-5">
    <v-switch
      v-model="switch1"
      inset
      
    ></v-switch>
    
  </v-sheet>
</template>

<script>
  export default {
    data () {
      return {
        switch1: true,
        switch2: false,
      }
    },
  }
</script>