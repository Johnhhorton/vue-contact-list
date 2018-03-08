<template>
  <div>
  <h2>Create Contact</h2>
    <input type="text" v-model="phone" placeholder="Phone">
    <input type="text" v-model="email" placeholder="Email">
    <button @click="submitForm">Create</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      phone: "",
      email: ""
    };
  },
  created() {
    this.resetForm();
  },
  methods: {
    resetForm() {
      this.phone = "";
      this.email = "";
    },
    submitForm() {
      //Veevalidate seems to have some features for checking if there are no errors.
      //Use that here.

      this.$emit("created", {
        id: this.email, //use some other form to create a unique id. Generally created when posting to backend.
        phone: this.phone,
        email: this.email
      });
      this.resetForm();
    }
  }
};
</script>
