<template>
  <div id="app">
    <div class="container">
      <div class="title">
        <h1>Typing Game</h1>
        <div class="marker"></div>
      </div>
      <button class="startButton mb-20">START</button>
      <div class="question mb-20">apple</div>
      <div class="clear">CLEAR!</div>
      <div class="typeFormWrapper mb-20">
        <input type="text" class="typeForm">
      </div>

      <div class="gaugeWrapper">
        <div class="gauge"></div>
      </div>
      <div>1/5</div>
    </div>
  </div>
</template>

<script>

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
