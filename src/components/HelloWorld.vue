<template>
  <div class="container">
    <section class="vote">
      <h3 class="give-your-vote">
        Silahkan Berikan Penilaian anda terhadap pelayanan anda
      </h3>
      <div class="emoticons">

      </div>
    </section>
    <section class="finish">
      Terimakasih telah memberi penilaian anda
    </section>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
  display: flex;
  height: 100vh;
  align-items: center;
  
  flex-wrap: wrap;
  text-align: center;
}

section{
  width: 100%;
}
</style>
