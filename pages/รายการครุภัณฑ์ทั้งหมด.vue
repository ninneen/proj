<template>

  <v-container>
    <v-div>
      <h2>รายการครุภัณฑ์ทั้งหมด</h2>
    </v-div>
    <br>
     <v-container fluid>
       
     <v-row align="center">
       <h4>เลือกห้อง</h4>
      <v-col
        class="d-flex"
        cols="8"
        sm="3"
      ><v-select
          :items="items"
          label="building"
          dense
          height="0.5px"
          width="1px"
          outlined
        ></v-select>
       </v-col>
       
       <v-col
        class="d-flex"
        cols="8"
        sm="3"
      ><v-select
          :items="items"
          label="room"
          dense
          outlined
        ></v-select>
      </v-col>
      
      
     

      </v-row>
      
    </v-container>

   <v-card-title>
    <upload-btn icon>
  <template slot="icon">
    <v-icon>add</v-icon>
  </template>
</upload-btn>
      <!--List -->
      <v-spacer></v-spacer>
      <div class="text-right">
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
      </div>
    </v-card-title>
 
   <v-data-table
    v-model="selected"
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    :search="search"
    class="elevation-1"
  >
  </v-data-table>
  </v-container>
</template>


<script>

  import UploadButton from 'vuetify-upload-button'

  export default {
    methods: {
      update (file) {
        // handle file here. File will be an object.
        // If multiple prop is true, it will return an object array of files.
      }
    },
    components: {
      'upload-btn': UploadButton
    }
  }

  import Vue from 'vue'
import Vuetify from 'vuetify/lib'
import { Ripple } from 'vuetify/lib/directives'

Vue.use(Vuetify, {
  // other stuff
  directives: {
    Ripple
  }
})

  export default {
    data () {
      return {
        search: '',
        selected: [],
        headers: [
          {
            text: 'No',
            align: 'start',
            sortable: false,
            value: 'no',
          },
          { text: 'Name', value: 'name' },
          { text: 'LastName', value: 'lastname' },
          { text: 'Code', value: 'code' },
          { text: 'Name_eq', value: 'name_eq' },
          { text: 'Room', value: 'room' },
          { text: 'Start_date', value: 'Start_date' },
          { text: 'Status', value: 'status' },
          { text: 'Note', value: 'note' },
          ],
          desserts: [
          {
            no: '1',
            name: 'Kaa',
            lastname: 'Waa',
            code: 159,
            name_eq: 'Camera',
            room: 'S1',
            start_date: 23042021,
            status: 'Accept',
            Note: '',
          },
          {
            no: '1',
            name: 'ga',
            lastname: 'Waa',
            code: 159,
            name_eq: 'Camera',
            room: 'S1',
            start_date: 23042021,
            status: 'Accept',
            Note: '',
          },
           {
            no: '1',
            name: 'la',
            lastname: 'Waa',
            code: 159,
            name_eq: 'Camera',
            room: 'S1',
            start_date: 23042021,
            status: 'Accept',
            Note: '',
          },
          {
            no: '1',
            name: 'va',
            lastname: 'Waa',
            code: 159,
            name_eq: 'Camera',
            room: 'S1',
            start_date: 23042021,
            status: 'Accept',
            Note: '',
          },
          {
            no: '1',
            name: 'saa',
            lastname: 'Waa',
            code: 159,
            name_eq: 'Camera',
            room: 'S1',
            start_date: 23042021,
            status: 'Accept',
            Note: '',
          },
          ]
       }
    },
  }
</script>
 
   <v-data-table
    v-model="selected"
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    :search="search"
    :single-select="singleSelect"
    item-key="no"
    show-select
    class="elevation-1"
  >
   
  </v-data-table>
  </v-container>
</template>

<script type="text/javascript" src="node_modules/vuejs/dist/vue.min.js"></script>
<script type="text/javascript" src="node_modules/vuetify-upload-button/dist/upload-button.min.js"></script>
<script type="text/javascript">
  Vue.use(UploadButton);
</script>
<script>

  export default {
    data () {
      return {
        search: '',
        selected: [],
        headers: [
          {
            text: 'No',
            align: 'start',
            sortable: false,
            value: 'no',
          },
          { text: 'Code', value: 'code' },
          { text: 'Image', value: 'image' },
          { text: 'Name', value: 'name' },
          { text: 'Status', value: 'status' },
          { text: 'Number_date', value: 'number_date' },
          { text: 'Note', value: 'note' },
          ],
          desserts: [
          {
            no: '1',
            code: 159,
            image: '',
            name: 'computer',
            status: 'ว่าง',
            number_date: 3,
            Note: '',
          },
          {
            no: '2',
            code: 159,
            image: '',
            name: 'Table',
            status: 'ว่าง',
            number_date: 3,
            Note: '',
          },
           {
            no: '3',
            code: 159,
            image: '',
            name: 'Notebook',
            status: 'ว่าง',
            number_date: 3,
            Note: '',
          },
          ]
       }
    },
  }
</script>


<style>
  .custom-loader {
    animation: loader 1s infinite;
    display: flex;
  }
  @-moz-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @-webkit-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @-o-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
</style>