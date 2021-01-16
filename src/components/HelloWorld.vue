<template>
  <div class="container">
    <section class="vote">
      <h3 class="give-your-vote">
        Silahkan Berikan Penilaian anda terhadap pelayanan anda
      </h3>
      <div class="emoticons">
        <Vote/>
      </div>
    </section>
    <section class="finish">
      Terimakasih telah memberi penilaian anda
    </section>
  </div>
</template>

<script>
import Vote from './Vote'
export default {
  name: 'HelloWorld',
  components: {
    Vote
  },
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

.give-your-vote{
  font-size: 21px;
}

section{
  width: 100%;
}

.emoticons{
  display: flex;
  justify-content: center;
}
</style>
