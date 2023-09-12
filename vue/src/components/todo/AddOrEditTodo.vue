<template>
  <v-card-text>
    <v-text-field
      v-if="!isEditMode"
      v-model="todoText"
      density="compact"
      label="Add Product"
      @keydown.enter="onKeyDown"
    ></v-text-field>

    <v-text-field
      v-else
      v-model="updateTodo.todo"
      density="compact"
      label="Edit Product"
      focused
      @keydown.enter="onEditKeyDown"
    ></v-text-field>
    
<v-text-field
  v-if="!isEditMode"
  v-model="todoText2"
  density="compact"
  label="Product Image Adresse"
  @keydown.enter="onKeyDown2"
></v-text-field>

<v-text-field
  v-else
  v-model="updateTodo2.todo"
  density="compact"
  label="Product Image Adresse"
  focused
  @keydown.enter="onEditKeyDown2"
></v-text-field>

  </v-card-text>
</template>

<script>
export default {
  data() {
    return {
      todoText: "",
      updateTodo: {},
      todoText2: "",
      updateTodo2: {},
    };
  },
  props: {
    isEditMode: {
      type: Boolean,
    },
    item: {
      type: Object,
    },
  },
  methods: {
    onKeyDown() {
      this.$emit("item-entered", this.todoText);
      this.todoText = "";
    },
    onEditKeyDown() {
      this.$emit("item-edited", this.updateTodo);
    },
    onKeyDown2() {
    this.$emit("item-entered", this.todoText2);
    this.todoText2 = "";
  },
  onEditKeyDown2() {
    this.$emit("item-edited", this.updateTodo2);
  },
  },
  mounted() {
    if (this.item?._id) {
      this.updateTodo = { ...this.item };
    }
  },
};
</script>

<style></style>
