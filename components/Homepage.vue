<template>
  <section class="container flex flex-col v-center h-center">
    <a href="#" class="flex flex-row col-gap-12 pv-12 ph-32">
      <img
        src="~assets/img/fastboilerplate.png"
        width="54"
        height="64"
        alt="fastboi logo"
      />
      <h1 class="f-64 p-0 m-0">FASTBOI</h1>
    </a>
    <div class="card shadow full-width ph-16">
      <p>
        <span class="f-bold f-blue">Fast boi</span>lerplate is based on Nuxt
        framework. Setup and customized for any rapid frontend development.
      </p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HomepageComponent',
}
</script>

<style lang="scss" scoped>
.container {
  margin-top: 15%;
}
.card {
  background: #fff;
  border-radius: 4 px;
  max-width: 460px;
}
</style>
