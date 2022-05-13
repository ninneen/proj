<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" clipped fixed app
    color="indigo lighten-5">
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
      
    </v-navigation-drawer>

    <v-app-bar clipped-left fixed app color="indigo darken-4">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" 
      color="indigo lighten-5"/>
      <v-avatar>
        <img src="image/logo.png" alt="logo"/>
      </v-avatar>
      <v-toolbar-title v-text="title" />
      <v-spacer />

      
    <v-card-text color="white">
      <h3 class="text-lg-right white--text font-weight-light"  >Name Surname</h3>
      <h4 class="text-lg-right white--text font-weight-light" >Admin</h4>
        
    </v-card-text>
  

     <v-avatar color="indigo">
      <v-icon dark>
        mdi-account-circle
      </v-icon>
    </v-avatar>
      

       

     
      </v-menu>
    </v-app-bar>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>


  </v-app>
  
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-view-grid-outline",
          title: "รายการครุภัณฑ์ทั้งหมด",
          to: "/รายการครุภัณฑ์ทั้งหมด",
        },

        {
          icon: "mdi-account-supervisor",
          title: "รายการสมาชิก",
          to: "/รายการสมาชิก",
        },
        {
          icon: "mdi-book-open",
          title: "ประวัติการยืม-คืนทั้งหมด",
          to: "/ประวัติการยืม-คืนทั้งหมด",
        },
        {
          icon: "mdi-equalizer-outline",
          title: "Dashboard",
          to: "/Dashboard",
        },
        {
          icon: "mdi-apps",
          title: "karu",
          to: "/karu",
        },
        {
          icon: "mdi-apps",
          title: "free",
          to: "/free",
        },
      ],

      miniVariant: false,
      right: true,
      rightDrawer: false,
    };
  },
};
</script>
