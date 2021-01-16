<template>
  <div class="buttons">
       <button v-for="(emoticon, index) in emoticons" 
          :key="index" 
          :id="emoticon"
          :value="emoticon"
          class="btn-emoticon"
          :class = "{active: emoticon === emoticonClick}"
          @click="vote"
          :disabled="isDisabled"
          >

       </button>
  </div>
</template>

<script>
import moment from 'moment'

export default {
  name: 'HelloWorld',
  props: {
       voteProp: {
            type: Function
       }
  },
  data () {
    return {
         emoticons: ['very-bad', 'bad', 'oke', 'good','very-good'],
         emoticonClick : ''
    }
  },
  methods:{
       vote(e){
               let voted = e.target.value
               //   untuk menentukan button di match dengan nilai key apakah sama atau tidak
               this.emoticonClick = e.target.value

               //melakukan penyimpanan
               this.store(e);

               //Melakukan emit nilai melalui HelloWorld componennts
               this.voteProp();
       },
       store(e){
            this.emoticonClick = e.target.value
            let voted = e.target.value
            let date = moment().format('YYYY-MM-DD')
            let key = moment().format('YYYYMMDDhhmmss')
            let data = {
                 vote: voted,
                 created_at: date
            }

            let json = JSON.stringify(data)

            localStorage.setItem(key, json)
       }
  },
  computed: {
       isDisabled : function(){
            return this.emoticonClick.length === 0 ? false : true
       }
  },
  mounted() {
       this.$root.$on('emitProsesDone', () => {
            this.emoticonClick = ''
       })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
     .buttons{
          display: flex
     }

     .btn-emoticon{
          background: url('~@/assets/logo.png');
          width: 100px;
          height: 100px;
          margin: 0px 10px;
          border: none;
          outline: none;
          cursor:pointer
     }

     #very-bad{
     background-position: 0px 0px;
     }

     #very-bad:hover{
     background-position: 0px -100px;
     }

     #very-bad.active,
     #very-bad:active{
     background-position: 0px -200px;
     }

     #bad{
     background-position: 100px 0px;
     }

     #bad:hover{
     background-position: 100px -100px;
     }

     #bad.active,
     #bad:active{
     background-position: 100px -200px;
     }

     #oke{
     background-position: 200px 0px;
     }

     #oke:hover{
     background-position: 200px -100px;
     }

     #oke.active,
     #oke:active{
     background-position: 200px -200px;
     }

     #good{
     background-position: 300px 0px;
     }

     #good:hover{
     background-position: 300px -100px;
     }

     #good:active{
     background-position: 300px -200px;
     }

     #very-good{
     background-position: 400px 0px;
     }

     #very-good:hover{
     background-position: 400px -100px;
     }

     #very-good:active{
     background-position: 400px -200px;
     }
</style>
