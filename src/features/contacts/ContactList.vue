<template>
<div>
  <h2>Contacts</h2>
  <ul v-if="contacts.length > 0">
    <li v-for="contact in contacts" :key="contact.email">
      {{contact.phone}} {{contact.email}} <button @click="remove(contact.id)">Delete</button>
    </li>
  </ul>
  <p v-else>
  You do not have any contacts. Create one below.
  </p>
</div>  
</template>
<script>
export default {
  name: "contact-list",
  props: ["contacts"],
  methods: {
    remove(id) {
      this.$emit("remove", id);
    }
  }
};
</script>
