<template>
  <div id="app">
    <ContactList :contacts="contacts" @remove="removeContact"/>
    <ContactCreate @created="addContact"/>
  </div>
</template>
<script>
/**
 * This is a self contained feature of your app.
 */
import ContactList from "./ContactList";
import ContactCreate from "./ContactCreate";

export default {
  name: "contacts",
  data() {
    return {
      contacts: []
    };
  },
  methods: {
    addContact(contact) {
      this.contacts.push(contact);
    },
    removeContact(id) {
      this.contacts = this.contacts.filter(contact => contact.id !== id);
    }
  },
  components: {
    ContactList,
    ContactCreate
  }
};
</script>
