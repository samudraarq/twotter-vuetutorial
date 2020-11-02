<template>
  <div class="card">
    <div class="username">@{{ user.username }} - {{ fullName }}</div>
    <div class="admin-badge" v-if="user.isAdmin">Admin</div>
    <div class="followers"><strong>followers:</strong> {{ followers }}</div>
    <button @click="followUser">Follow</button>
  </div>
  <div class="twoots-wrapper">
    <TwootItem
      v-for="twoot in user.twoots"
      :key="twoot.id"
      :username="user.username"
      :twoot="twoot"
      @favourite="toggleFavourite"
    />
  </div>
</template>

<script>
import TwootItem from "./TwootItem";
export default {
  name: "UserProfile",
  data() {
    return {
      followers: 0,
      user: {
        id: 1,
        username: "Samudra_arq",
        firstName: "Samudra",
        lastName: "Arqam",
        email: "samudrafaris@gmail.com",
        isAdmin: true,
        twoots: [
          { id: 1, content: "Twooter is amazing!" },
          { id: 2, content: "Hello from Twooter" },
        ],
      },
    };
  },
  components: {
    TwootItem,
  },
  watch: {
    followers(newFollowerCount, oldFollowerCount) {
      if (oldFollowerCount < newFollowerCount) {
        console.log(`${this.user.username} has gain a follower!`);
      }
    },
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
  },
  methods: {
    followUser() {
      this.followers++;
    },
    toggleFavourite(id) {
      console.log(`Just favorutied #${id}`);
    },
  },
  mounted() {
    this.followUser();
  },
};
</script>

<style scoped>
.card {
  padding: 2rem 3rem;
  border: 1px solid #f0f0f0;
  border-radius: 5px;
  display: inline-block;
  font-size: 1.2rem;
  background: #fff;
}

button {
  padding: 0.5rem 1rem;
}

.admin-badge {
  background: salmon;
  font-size: 1rem;
  padding: 0 10px;
  border-radius: 3px;
  margin-right: auto;
  display: inline-block;
}

.twoots-wrapper {
  justify-self: stretch;
}
</style>>
