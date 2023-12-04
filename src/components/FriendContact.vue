<template>
  <h2>{{ name }} {{ favtchange === "1" ? "(Favourite)" : "" }}</h2>
  <button @click="togglefavt">Toggle Favt</button>
  <button @click="togglebtn">Show Details</button>
  <ul v-if="detailsVisible">
    <li><strong>Email</strong> {{ emailAddress }}</li>
    <li><strong>Phone Number</strong> {{ phoneNumber }}</li>
  </ul>
</template>

<script>
export default {
  props: ["name", "emailAddress", "phoneNumber", "isFavt"],
  data() {
    return {
      friend: {
        name: "Hammad",
        id: 231123,
        phone: 213213,
        email: "Hammad@gmail.com",
      },
      detailsVisible: false,
      favtchange: this.isFavt,
    };
  },
  methods: {
    togglebtn() {
      this.detailsVisible = !this.detailsVisible;
    },
    togglefavt() {
      if (this.favtchange == "1") {
        this.favtchange = "0";
      } else {
        this.favtchange = "1";
      }
    },
  },
};
</script>