<template >
  <div>
    <header>COUNTDOWN</header>
    <h2 v-if="game === 0">CHOOSE YOUR GAME</h2>
    <section >
      <button v-if="game === 0" @click="gameSelect('Letters')">Letters</button>
      <button v-if="game === 0" @click="gameSelect('Numbers')">Numbers</button>
      <button v-if="game === 0" @click="gameSelect('Conundrum')">Conundrum</button>
      <button v-if="game === 0" @click="gameSelect('Full Game')">Full Game</button>
      <h1 v-if="fullGame">Round {{currentRoundNumber}}</h1>
      <letter-round v-if="game === 'Letters'" :players="players" :fullGame="fullGame" />
      <conundrum v-if="game === 'Conundrum'" :players="players" :fullGame="fullGame"/>
      <number-round v-if="game === 'Numbers'" :players="players" :fullGame="fullGame"/>
      <p id="total-div"></p>
    </section>
  </div>  
</template>

<script>
import LetterRound from '@/components/LettersRound.vue'
import ConundrumRound from '@/components/ConundrumRound.vue'
import NumbersRound from '@/components/NumbersRound.vue'

import {eventBus} from '@/main.js'
  export default {
    data(){
      return {
        game: 0,
        currentRoundNumber: 0,
        fullGameRounds: ['Letters', 'Numbers', 'Conundrum'],
        fullGame: false,
        players: [{name: 'Player One', word: "", score: 0},{name: 'Player Two', word: "", score: 0}]
      }
    },
    components:{
      'letter-round': LetterRound,
      'conundrum': ConundrumRound,
      'number-round': NumbersRound
    },
    methods:{
      gameSelect(gameNumber){
        this.game = gameNumber
        if (gameNumber === 'Full Game'){
          this.game = 'Letters'
          this.fullGame = true
          this.currentRoundNumber = 1
        }
      }
    },
    mounted(){
      eventBus.$on('next-round', () => {
        this.currentRoundNumber++
        this.game = this.fullGameRounds[this.currentRoundNumber-1]
      })

      eventBus.$on('add-scores', (score) => {
        this.players.filter((player) => {
          if (player.name === score.name){
            player.score += score.score
          }
        })
      })
      
    }
  }

</script>

<style lang="css" scoped>

* {
  font-family: sans-serif;
  background-color: #ADD8E6;
}

#total-div {
  height: 300px;
}

button {
  box-shadow:inset 0px 1px 0px 0px #97c4fe;
	background:linear-gradient(to bottom, #3d94f6 5%, #1e62d0 100%);
	background-color:#3d94f6;
	border-radius:6px;
	border:1px solid #337fed;
	display:inline-block;
	cursor:pointer;
	color:#ffffff;
	font-family:Arial;
	font-size: large;
	font-weight:bold;
	padding:6px 24px;
	text-decoration:none;
	text-shadow:0px 1px 0px #1570cd;
  margin: 20px 40px;
  width: 180px;
  height: 100px

}

button:hover {
	background:linear-gradient(to bottom, #1e62d0 5%, #3d94f6 100%);
	background-color:#1e62d0;
}
button:active {
	position:relative;
	top:1px;
}

header {
  font-size: 120px;
  text-align: center;
  padding: 10px;
  color: #004e98;
  font-weight: 700;
  text-shadow: 0 0 3px white;
}

section {
  text-align: center;
}


h2 {
  font-size: 60px;
  text-align: center;
  margin: 0px;
  color: white;
  text-shadow: 0 0 5px #034078;
  margin-top: 50px;
  margin-bottom: 50px;
  margin-left: 20px;
  margin-right: 20px;

}



</style>