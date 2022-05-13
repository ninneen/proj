<template>
  <v-container>
    <v-div>
      <h2>รายการสมาชิก</h2>
    </v-div>
    <br />
    <v-container fluid>
      <v-row align="center">
        <h4>ปีการศึกษา</h4>
       
      </v-row>
    </v-container>

    <v-card-title>
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
      <template v-slot:item.status="{ item }">
        <v-switch v-model="resolve" inset dense color="red darken-3">
          <template #prepend>
            <p class="small"></p>
          </template>
        </v-switch>
      </template>
    </v-data-table>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      search: "",
      selected: [],
      headers: [
        {
          text: "No",
          align: "start",
          sortable: false,
          value: "no",
        },
        { text: "ID", value: "id" },
        { text: "Name", value: "name" },
        { text: "Surname", value: "surname" },
        { text: "Major", value: "major" },
        { text: "E-mail", value: "email" },
        { text: "Status", value: "status" },
      ],
      desserts: [
        {
          no: "1",
          id: 6231501001,
          image: "",
          name: "Kan",
          surname: "Chan",
          major: "CE",
          email: "6231501001@lamduan.mfu.ac.th",
          status: false,
        },
        {
          no: "2",
          id: 6231501013,
          image: "",
          name: "Nut",
          surname: "K",
          major: "SE",
          email: "6231501013@lamduan.mfu.ac.th",
          status: false,
        },
        {
          no: "3",
          id: 6231501037,
          image: "",
          name: "Poon",
          surname: "C",
          major: "MTA",
          email: "6231501037@lamduan.mfu.ac.th",
          status: false,
        },
      ],
    };
  },
};
</script>

<style>
v-input.v-input--switch--inset .v-input--switch__track:after {
  content: "On";
  color: #000000;
  font-size: 13px;
}

.v-input.v-input--switch--inset.v-input--is-label-active.v-input--is-dirty
  .v-input--switch__track:after {
  content: "Off";
  color: #ffffff;
  font-size: 13px;
}

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