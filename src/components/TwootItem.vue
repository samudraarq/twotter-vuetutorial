<template>
  <div class="twootItem" @click="favouriteTwoot(twoot.id)">
    <div class="username">@{{ username }}</div>
    <div class="twoot">{{ twoot.content }}</div>
  </div>
</template>

<script>
export default {
  name: "TwootItem",
  props: {
    username: {
      type: String,
      required: true,
    },
    twoot: {
      type: Object,
      required: true,
    },
  },
  methods: {
    favouriteTwoot(id) {
      this.$emit("favourite", id);
    },
  },
};
</script>

<style scoped>
.twootItem {
  background: #fff;
  border-radius: 3px;
  margin: 1rem 0;
  padding: 1rem;
  font-size: 1.2rem;
}
</style>