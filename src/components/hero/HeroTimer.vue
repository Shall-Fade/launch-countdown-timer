<template>
  <div class="timer-container">
    <div class="timer-group">
      <div class="timer-card">
        <p>
          {{ timeDays }}
        </p>
      </div>
      <h4 class="timer-subtitle">Days</h4>
    </div>
    <div class="timer-group">
      <div class="timer-card">
        <p>
          {{ timeHours }}
        </p>
      </div>
      <h4 class="timer-subtitle">Hours</h4>
    </div>
    <div class="timer-group">
      <div class="timer-card">
        <p>
          {{ timeMinutes }}
        </p>
      </div>
      <h4 class="timer-subtitle">Minutes</h4>
    </div>
    <div class="timer-group">
      <div class="timer-card">
        <p>
          {{ timeSeconds }}
        </p>
      </div>
      <h4 class="timer-subtitle">Seconds</h4>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    // Переменные
    const timeDays = ref(0);
    const timeHours = ref(0);
    const timeMinutes = ref(0);
    const timeSeconds = ref(0);

    // Таймер
    function countdownTimer() {
      const endDate = new Date("January 1, 2023 00:00:00");
      const currentDate = new Date();
      const timeLeft = endDate - currentDate;

      const seconds = 1000;
      const minutes = 60 * seconds;
      const hours = 60 * minutes;
      const days = 24 * hours;

      timeDays.value = Math.floor(timeLeft / days);
      timeHours.value = Math.floor((timeLeft % days) / hours);
      timeMinutes.value = Math.floor((timeLeft % hours) / minutes);
      timeSeconds.value = Math.floor((timeLeft % minutes) / seconds);

      timeDays.value =
        timeDays.value < 10 ? "0" + timeDays.value : timeDays.value;
      timeHours.value =
        timeHours.value < 10 ? "0" + timeHours.value : timeHours.value;
      timeMinutes.value =
        timeMinutes.value < 10 ? "0" + timeMinutes.value : timeMinutes.value;
      timeSeconds.value =
        timeSeconds.value < 10 ? "0" + timeSeconds.value : timeSeconds.value;
    }

    setInterval(countdownTimer, 1000);

    return {
      timeDays,
      timeHours,
      timeMinutes,
      timeSeconds,
    };
  },
};
</script>

<style scoped>
.timer-container {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.timer-group {
  margin: 0 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.timer-card {
  position: relative;
  background: linear-gradient(
    var(--c-dark-desaturated-dark-blue) 50%,
    var(--c-dark-desaturated-blue) 50%
  );
  padding: 15px 20px;
  min-width: 150px;
  text-align: center;
  border-radius: 10px;
  font-size: 72px;
  color: var(--c-soft-red);
  margin-bottom: 25px;
  box-shadow: 0 7px var(--c-very-dark-black-blue);
}
.timer-card p {
  letter-spacing: 3px;
}
.timer-card::before {
  content: "";
  position: absolute;
  width: 5%;
  height: 8%;
  left: 0;
  top: 45%;
  background-color: var(--c-very-dark-black-blue);
  border-radius: 0 80% 80% 0;
}
.timer-card::after {
  content: "";
  position: absolute;
  width: 5%;
  height: 8%;
  right: 0;
  top: 45%;
  background-color: var(--c-very-dark-black-blue);
  border-radius: 80% 0 0 80%;
}
/* .top,
.bottom,
.timer-card.card::after,
.timer-card.card::before {
  height: 0.75em;
  line-height: 1;
  padding: 0.25em;
  overflow: hidden;
}
.timer-card.card::before {
  position: absolute;
  content: "19";
  animation: flip-top 0.5s ease-in;
  transform-origin: bottom;
}
@keyframes flip-top {
  100% {
    transform: rotateX(90deg);
  }
}
.timer-card.card::after {
  position: absolute;
  bottom: 0;
  content: "19";
  transform: rotateX(90deg);
  animation: flip-bottom 0.5s ease-out 0.5s;
  transform-origin: top;
}
@keyframes flip-bottom {
  100% {
    transform: rotateX(0deg);
  }
}
.top,
.timer-card.card::before {
  background-color: var(--c-dark-desaturated-dark-blue);
  border-radius: 10px 10px 5px 5px;
}
.bottom,
.timer-card.card::after {
  display: flex;
  align-items: flex-end;
  background-color: var(--c-dark-desaturated-blue);
  border-radius: 5px 5px 10px 10px;
}
.bottom {
  box-shadow: 0 7px var(--c-very-dark-black-blue);
} */
.timer-subtitle {
  text-transform: uppercase;
  font-size: 13px;
  color: var(--c-grayish-blue);
  letter-spacing: 5px;
}
/* Адаптив */
@media only screen and (max-width: 1024px) {
  .timer-card {
    min-width: 120px;
    font-size: 52px;
  }
}
@media only screen and (max-width: 768px) {
  .timer-group {
    margin: 0 10px;
  }
  .timer-card {
    min-width: 75px;
    font-size: 28px;
  }
  .timer-subtitle {
    font-size: 10px;
  }
}
@media only screen and (max-width: 425px) {
  .timer-card {
    min-width: 60px;
    padding: 10px 15px;
    font-size: 20px;
  }
  .timer-subtitle {
    font-size: 8px;
  }
}
</style>
