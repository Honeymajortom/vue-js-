<template>
  <div class="circular-progress">
    <svg class="progress-ring" width="500" height="500">
      <circle
        class="progress-ring-circle"
        :stroke-dasharray="circumference"
        :stroke-dashoffset="dashOffset"
        cx="300"
        cy="300"
        r="180"
      />
    </svg>
    <div class="progress-text">{{ progress }}%</div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      progress: 0,
    }
  },
  computed: {
    circumference() {
      return 2 * Math.PI * 180; // Assuming a radius of 40
    },
    dashOffset() {
      const progressDecimal = this.progress / 100;
      return this.circumference * (1 - progressDecimal);
    },
  },
  mounted() {
    this.updateProgress();
  },
  methods: {
    updateProgress() {
      setInterval(() => {
        this.targetProgress = Math.floor(Math.random() * 101); 
      }, 500); 

      setInterval(() => {
        if (this.progress < this.targetProgress) {
          this.progress += 1;
        } else if (this.progress > this.targetProgress) {
          this.progress -= 1;
        }
      }, 10);
    },
  }
};
</script>

<style scoped>
.circular-progress {
  text-align: center;
}

.progress-ring {
  transform: rotate(90deg);
}

.progress-ring-circle {
  fill: transparent;
  stroke: #7a56cf; /* Progress bar color */
  stroke-width: 20; /* Width of the progress bar */
}

.progress-text {
  font-size: 20px;
  font-weight: bold;
  margin-top: 10px;
  color: aliceblue;
}
</style>
