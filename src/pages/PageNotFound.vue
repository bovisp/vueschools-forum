<template>
  <div class="col-ful">
    <h1>Not found</h1>

    <p>
      Oooops. We couldn't find what you were loking for. Why don't you 
      <router-link :to="{name: 'Home'}">go home instead</router-link>?
    </p>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
  h1 {
    font-size: 100px;
  }
  p {
    font-size: 50px;
    font-weight: 300;
  }
</style>