<template>
  <div id="app">
    <div class="container">
      <div class="title">
        <h1>Typing Game</h1>
        <div class="marker"></div>
      </div>
      <button v-if="startFlg!=true" class="startButton mb-20" @click="gameStart">START</button>
      <div v-if="startFlg">
        <div class="question mb-20">{{ current_question }}</div>
        <div v-if="current_question_counts == question_counts" class="clear">CLEAR!</div>
        <div class="typeFormWrapper mb-20">
          <input v-model="typeBox" type="text" class="typeForm">
        </div>

        <div class="gaugeWrapper mb-20">
          <div v-bind:style="styleObject" class="gauge"></div>
        </div>
        <div>{{ current_question_counts }}/{{ question_counts }}</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "main",
    data() {
      return {
        startFlg: "",
        current_question: "",
        questions: [
          'apple',
          'banana',
          'chocolate',
          'donut',
          'espresso'
        ],
        typeBox: "",
        current_question_counts: 0,
        question_counts: 0
      }
    },
    // computed
    methods: {
      gameStart() {
        this.startFlg = true
      }
    },
    mounted() {
      this.current_question = this.questions[0]
      this.question_counts = this.questions.length
    },
    watch: {
      typeBox(e) {
        if (e == this.current_question) {
          this.questions.splice(0,1)
          this.current_question = this.questions[0]
          this.typeBox = ""
          this.current_question_counts = this.current_question_counts + 1
        }
      }
    }
  }

</script>

<style>
  *{
    font-family: inherit;
    font-size: inherit;
    line-height: inherit;
  }

  .container {
    width: 400px;
    margin: 0 auto;
    text-align: center;
  }

  .title {
    position: relative;
    font-size: 48px;
  }

  .marker {
    width: 100%;
    height: 35%;
    background: #a2a2a270;
    position: absolute;
    bottom: 5%;
    z-index: -1;
  }

  .startButton {
    background: #333;
    color: #fff;
    padding: 4px 60px;
    border: none;
    outline: none;
    border-radius: 8px;
    cursor: pointer;
  }

  .startButton:hover {
    opacity: 0.7;
  }

  .question {
    color: gray;
  }

  .clear {
    color: #03a9;
  }

  .typeForm {
    outline: none;
    border: none;
    text-align: center;
  }

  .typeFormWrapper {
    border-bottom: 1px solid gray;
  }

  .gauge {
    height: 12px;
  }

  .gaugeWrapper {
    border: 1px solid;
    height: 12px;
  }
</style>
