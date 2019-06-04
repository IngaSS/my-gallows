<template>
  <div id="app">
    <InputField :accept="this.accept" v-if="!show" v-model="inputText"></InputField>
    <InputLetterField :submitLetter="this.submitLetter" v-if="show" v-model="inputText">OK</InputLetterField>
    <Letters :wordUnits="this.wordUnits"></Letters>
    <Score :img="imgCart" :errors="this.errors" v-if="show"></Score>
    <FailedLetters :wrongLetters="this.wrongLetters" v-if="show"/>
    <Newgame :startNewGame="this.startNewGame" v-if="showBtn"/>
  </div>
</template>

<script>
import InputField from "./components/InputField";
import Letters from "./components/Letters";
import InputLetterField from "./components/InputLetterField";
import FailedLetters from "./components/FailedLetters";
import Score from "./components/Score";
import Newgame from "./components/NewGame";
import pics from "./pics.json";

export default {
  name: "app",
  components: {
    InputField,
    Letters,
    InputLetterField,
    Score,
    Newgame,
    FailedLetters
  },
  data() {
    return {
      inputText: "",
      word: "",
      letters: [],
      wrongLetters: [],
      wordUnits: [],
      show: false,
      score: 12,
      imgCart: require("../img/pic1.png"),
      errors: 0,
      showBtn: false
    };
  },

  methods: {
    accept() {
      this.word = this.inputText.toLowerCase();
      this.letters = this.word.split("");
      let unit;
      this.letters.forEach(letter => {
        unit = Object.assign({}, { letter: letter, checked: false });
        this.wordUnits.push(unit);
      });
      this.inputText = "";
      this.show = true;
    },

    submitLetter() {
      let letter = this.inputText.toLowerCase();
      this.wordUnits.forEach(elem => {
        if (elem.letter === letter) {
          elem.checked = true;
        }
      });

      if (
        !this.letters.includes(letter) &&
        !this.wrongLetters.includes(letter) &&
        !(letter == "")
      ) {
        this.errors++;
        this.wrongLetters.push(letter);
      }

      if (this.wordUnits.every(elem => elem.checked == true)) {
        this.imgCart = require("../img/youWin.png");
        this.showBtn = true;
      } else {
        for (let i = 0; i < this.errors; i++) {
          this.imgCart = require("../img/" + pics[i].img);
          if (this.errors >= pics.length) {
            this.imgCart = require("../img/go.png");
            this.wordUnits.forEach(elem => {
              elem.checked = true;
            });
            this.showBtn = true;
          }
        }
      }

      this.inputText = "";
    },

    startNewGame() {
      window.location.reload();
    }
  }
};
</script>

<style>
body {
  background-color: lightgray;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
