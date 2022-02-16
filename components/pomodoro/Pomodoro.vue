<template>
  <div
    class="
      absolute
      inset-0
      m-auto
      h-80
      w-80
      bg-gray-400
      flex flex-col
      rounded-full
      justify-center
    "
    typeof="pomodoro-wrap"
  >
    <span class="text-8xl self-center text-gray-50"
      >{{ minutesLeft }}:{{ secondsLeft }}
    </span>
    <button class="text-gray-50" @click="start()">play</button>
  </div>
</template>

<script>
export default {
  name: 'PomodoroTimer',
  data() {
    return {
      timeLeft: 1500,
      timerRunning: false,
    }
  },
  computed: {
    minutesLeft() {
      if (Math.floor(this.timeLeft / 60) === 0) {
        return '00'
      } else {
        return Math.floor(this.timeLeft / 60)
      }
    },
    secondsLeft() {
      if (this.timeLeft - this.minutesLeft * 60 === 0) {
        return '00'
      } else {
        return this.timeLeft - this.minutesLeft * 60
      }
    },
  },
  beforeMount() {},
  mounted() {
  },
  methods: {
    start() {
      if (this.timerRunning === false) {
        this.timerRunning = true
        this.interval = setInterval(() => {
          if (this.timeLeft === 0) {
            clearInterval(this.interval)
          } else {
            this.timeLeft--
          }
        }, 1000)
      }
    },
  },
}
</script>

<style>
</style>