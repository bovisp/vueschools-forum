<template>
  <div class="col-ful" :class="$style.centered">
    <h1 :class="$style.headingLarge">Not found</h1>

    <p :class="$style.textLarge">
      Oooops. We couldn't find what you were loking for. Why don't you 
      <router-link :to="{name: 'Home'}">go home instead</router-link>?
    </p>
  </div>
</template>

<script>
export default {}
</script>

<style module>
  .centered {
    text-align: center;
  }
  .headingLarge {
    font-size: 100px;
  }
  .textLarge {
    font-size: 50px;
    font-weight: 100;
  }
</style>