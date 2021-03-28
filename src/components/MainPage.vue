<template>
  <div class>
    <v-container>
      <div
        class="text-center font-weight-black text-md-h1 text-h2 mb-4 mb-md-8 pa-3"
      >
        Not Another Focus Timer
      </div>
      <div class="text-h6 text-center mb-12 font-italic">{{ quote }}</div>
      <div class="d-flex justify-center align-center">
        <v-row justify="center" align="center">
          <v-btn
            v-for="minutes in minutesArray"
            :key="minutes"
            class="ma-3"
            depressed
            dark
            rounded
            x-large
            color="black"
            @click="minuteButtonClicked(minutes)"
            >{{ minutes }} minutes</v-btn
          >
        </v-row>
      </div>
      <v-expand-transition>
        <div v-if="showTimer">
          <div class="text-h1 font-weight-bold text-center mt-12 mb-4">
            {{ formattedTimeLeft }}
          </div>
          <div class="d-flex justify-center">
            <v-btn
              class="ma-5 px-8"
              depressed
              dark
              large
              rounded
              color="red"
              @click="hideTimer()"
              >Stop</v-btn
            >
          </div>
        </div>
      </v-expand-transition>
    </v-container>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {
  showTimer = false;
  timeLimit = 1500;
  timePassed = 0;
  timerInterval = 0;
  minutesArray = [25, 55, 85];
  quotes = [
    "“The successful warrior is the average man, with laser-like focus.” - Bruce Lee",
    "“Lack of direction, not lack of time, is the problem.” ― Zig Ziglar",
    "“What you stay focused on will grow.” ― Roy T. Bennett",
    "“Where your attention goes, your time goes” ― Idowu Koyenikan",
    "“Focusing is about saying No.” ― Steve Jobs",
  ];

  minuteButtonClicked(minutes: number): void {
    this.showTimer = true;
    this.reset(minutes * 60);
    this.startTimer();
  }

  reset(seconds: number): void {
    this.timeLimit = seconds;
    this.timePassed = 0;
    if (this.timerInterval) clearInterval(this.timerInterval);
  }

  hideTimer(): void {
    this.showTimer = false;
    document.title = "Not Another Focus Timer";
    clearInterval(this.timerInterval);
  }

  async playAudio(): Promise<void> {
    const audio = new Audio(
      "https://soundbible.com/mp3/Air Plane Ding-SoundBible.com-496729130.mp3"
    );
    await audio.play();
  }

  startTimer(): void {
    this.timerInterval = setInterval(async () => {
      if (this.timeLeft > 0) {
        document.title = this.formattedTimeLeft + " - Work Work Work!";
        this.timePassed += 1;
      } else {
        document.title = "Phew - all done!";
        clearInterval(this.timerInterval);
        await this.playAudio();
        alert("Times up!");
      }
    }, 1000);
  }

  get timeLeft(): number {
    return this.timeLimit - this.timePassed;
  }

  get formattedTimeLeft(): string {
    const timeLeft = this.timeLeft;
    const minutes = Math.floor(timeLeft / 60);
    let seconds = timeLeft % 60;
    // Prefix with 0 when less than 10 seconds
    if (seconds < 10) {
      return `${minutes}:0${seconds}`;
    }
    // The output in MM:SS format
    return `${minutes}:${seconds}`;
  }

  get quote(): string {
    const randomNumber = Math.floor(Math.random() * 5);
    return this.quotes[randomNumber];
  }
}
</script>