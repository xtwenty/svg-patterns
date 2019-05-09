<template>
  <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
       :width="gridWidth"
       :height="gridHeight"
       :viewbox="`0 0 ${gridWidth} ${gridHeight}`">
    <square v-for="square in squares"
            v-bind:key="square.id"
            :width="square.size"
            :height="square.size"
            :x="square.x"
            :y="square.y"
            :style="square.style"
            :pattern="square.pattern">
    </square>
  </svg>
</template>

<script>
import Square from './Square.vue';
export default {
  name: 'Griddle',
  props: {
    msg: String,
    gridWidth: Number,
    gridHeight: Number,
    gridRows: Number,
    gridCols: Number
  },
  computed: {
    squares() {
      const size = this.gridWidth / this.gridCols;
      let squares = [];
      for (let i = 0; i < this.gridRows; i++) {
        for (let j = 0; j < this.gridCols; j++) {
          const sq = {
            size,
            y: i * size,
            x: j * size,
          };
          squares.push(sq)
        }
      }
      return squares;
    }
  },
  components: {
    Square
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
