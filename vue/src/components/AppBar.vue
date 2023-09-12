<template>
  <v-card class="mx-auto" max-width="448">
    <v-layout>
      <v-app-bar color="primary" density="compact">
        <template v-slot:prepend>
          <v-app-bar-nav-icon>
            <v-icon>mdi-home</v-icon>
          </v-app-bar-nav-icon>
          <v-app-bar-title>
            {{ userProp.name }} {{ userProp.surname }}..:
          </v-app-bar-title>
            <v-app-bar-title>
<router-link class="homePage" to="/">Ana Sayfa        
       </router-link></v-app-bar-title>
        </template>
<div v-if="isAdmin">
      <v-btn @click="goToAdmin">Admin</v-btn>
    </div>
        



        <v-btn @click="handleLogout">
          <v-icon>mdi-logout</v-icon>
          logout
        </v-btn>
      </v-app-bar>
    </v-layout>
  </v-card>
</template>

<script>
export default {
  props: {
    userProp: {
      type: Object,
      required: true,
    },
  },
  methods: {
    handleLogout() {
      this.$store.dispatch("userStore/logout");
    },
    goToAdmin() {
      this.$router.push("/admin");
    },
  },
   
  computed: {
    isAdmin() {
      return this.userProp && this.userProp.rol === "0";
    },
  },
};
</script>

<style>
.homePage{
  color:aliceblue;
}
</style>
