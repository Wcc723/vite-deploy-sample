<template>
  <div class="about">
    {{ data }}
    <button type="button" class="btn btn-primary">Primary</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: {},
    };
  },
  mounted() {
    console.log(import.meta.env.VITE_PATH);
    const url = import.meta.env.VITE_PATH;
    this.$http.get(url).then((res) => {
      console.log(res.data);
      this.data = res.data.results[0];
    });
  },
};
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
