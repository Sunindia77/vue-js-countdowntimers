<template>
  <div id="app">

    

    <h3>New Year: {{ deadline1 }}</h3>
    <flip-countdown :deadline="deadline1"></flip-countdown>
    

    <h3>Deadline2: {{ deadline2 }} (showDays = false, showHours = false)</h3>
    <flip-countdown
      :deadline="deadline2"
      :showDays="false"
      :showHours="false"
      @timeElapsed="timeElapsedHandler"
    ></flip-countdown>

  </div>
</template>

<script>
import FlipCountdown from "vue2-flip-countdown";
import moment from "moment";
const fmt = "YYYY-MM-DD HH:mm:ss";
export default {
  name: "app",
  components: {
    FlipCountdown,
  },
  data() {
    return {
      deadline1: moment()
        .add(23, "d")
        .add(10, "s")
        .format(fmt),
      deadline2: moment()
        .add(2, "h")
        .format(fmt),
     
    };
  },
  
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.more {
  margin: 30px 0;
}
button {
  margin: 10px;
}
</style>