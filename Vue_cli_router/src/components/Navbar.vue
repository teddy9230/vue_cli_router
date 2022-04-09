<template>
  <div>
    <nav>
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/about">About</router-link></li>
        <li><router-link to="/contact">Contact</router-link></li>
      </ul>
    </nav>

    <div>
      <ul>
        <li v-for="(id, index) in userIds" :key="index">
          <router-link :to="{ name: 'Profile', params: { user_id: id } }">
            profile {{ id }}
          </router-link>
        </li>
      </ul>

      <button @click="Home">Home</button>
      <button @click="About">About</button>
      <button @click="Contact">Contact</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      userIds: ["1", "2", "3", "4", "5", "6", "7", "8", "9", "0"],
    };
  },
  methods: {
    Home() {
      this.$router.push({ name: "Home" });
    },
    About() {
      this.$router.push({ name: "About" });
    },
    Contact() {
      this.$router.push({ name: "Contact" });
    },
  },
};
</script>

<style>
ul li {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
a.router-link-exact-active {
  color: red;
}
</style>
