<template>
    <svg class="square" :width="width" :height="height" :x="x" :y="y" :style="styleObj">
        <g class="bg">
            <rect :width="width" :height="height" :style="styleObj" />
            <circle :cx="circSize" :cy="circSize" :r="circSize" fill="rgba(0,0,0,0.1)"/>
        </g>
    </svg>
</template>

<script>
  export default {
    name: 'Square',
    props: {
      width: Number,
      height: Number,
      x: Number,
      y: Number,
    },
    computed: {
      styleObj() {
        return {
          fill: `hsla(${random(0, 360)}, 40%, 60%, 1)`
        }
      },
      circSize() {
        return this.width / 2;
      }
    }
  };

  function random(min, max) {
    if (max == null) {
      max = min;
      min = 0;
    }
    return min + (max - min) * Math.random();
  }
</script>