<template>
  <div>
    <p>{{ ip }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ip: "",
    };
  },
  mounted: function () {
    this.fetchSomething();
  },
  methods: {
    async fetchSomething() {
      const ip = await this.$axios.$get("http://icanhazip.com");
      this.ip = ip;
    },
  },
  async asyncData(context) {
    const id = context.params.id;
    console.log(id);
  },
};
</script>
