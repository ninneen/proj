<template>
  <v-container>
    <v-div>
      <h2>ประวัติการยืม-คืนทั้งหมด</h2>
    </v-div>
    <br />

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
      <template v-slot:item.detail="{ item }">
        <v-div class="my-2">
          <v-btn small color="primary" dark> Detail </v-btn>
        </v-div></template>
      
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
        { text: "Detail", value: "detail" },
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
          detail: "",
        },
        {
          no: "2",
          id: 6231501013,
          image: "",
          name: "Nut",
          surname: "K",
          major: "SE",
          email: "6231501013@lamduan.mfu.ac.th",
          detail: "",
        },
        {
          no: "3",
          id: 6231501037,
          image: "",
          name: "Poon",
          surname: "C",
          major: "MTA",
          email: "6231501037@lamduan.mfu.ac.th",
          detail: "",
        },
      ],
    };
  },
};
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