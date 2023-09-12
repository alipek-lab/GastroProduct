<template>
  <div class="home">
    <div class="mt-16">Home Page</div>
    <v-btn @click="onClick">Pizza Varieties</v-btn>
<div v-if="isAdmin">
      <v-btn @click="goToAdmin">Admindi</v-btn>
    </div>
  </div>
</template>
        
          
        
<script>
export default {

  methods: {

    onClick() {
      this.$router.push("/todo");
    },
  },

};

</script>
