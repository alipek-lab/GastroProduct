<template>
  <div class="home">
    <div class="mt-16">Home Page</div>
    <v-btn @click="onClick">Order Pizza</v-btn>

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
