<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>Em breve, um site novo para você.</p>
    <p>
      Para maiores informações, envie um e-mail para <b>contato@katalid.com</b>
    </p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
p {
  color: rgb(236, 226, 235);
  line-height: 3rem;
}
</style>
