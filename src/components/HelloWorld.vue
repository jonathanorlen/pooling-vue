<template>
  <div class="container">
    <section class="vote">
      <h3 class="give-your-vote">
        Silahkan Berikan Penilaian anda terhadap pelayanan anda
      </h3>
      <div class="emoticons">
        <Vote :voteProp="voteFun"/>
      </div>
    </section>
    <section class="finish">
      <transition name="fade"
        v-on:after-enter="resetVote"
      >
        <h4 v-if="show">  Terimakasih telah memberi penilaian anda</h4>
      </transition>
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
      msg: 'Welcome to Your Vue.js App',
      show: false
    }
  },
  methods: {
    voteFun(){
      this.show = true;
      console.log('chnage')
    },
    resetVote(){
      this.show = false
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

.fade-enter-active, .fade-leave-active{
  transition: opacity 1s
}

.fade-enter, .fade-leave-to{
  opacity: 0;
}

.emoticons{
  display: flex;
  justify-content: center;
}
</style>
