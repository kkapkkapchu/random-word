<template>
  <div
    class="word"
    @click="onClick"
  >
    <h1 class="noselect">{{value}}</h1>
  </div>
</template>

<script>
export default {
  name: "ShowWord",
  props: {
    data: {
      type: Array,
      default: () => []
    }
  },
  data() {
    return {
      value: "Start >",
      index: -1
    };
  },
  watch: {
    data: {
      handler() {
        (this.value = "Start >"), (this.index = -1);
      }
    }
  },
  methods: {
    onClick() {
      if (this.index === this.data.length - 1) {
        this.value = "The End.";
        return;
      }

      this.value = this.data[++this.index];
    }
  }
};
</script>

<style scoped>
.word {
  display: block;
  margin-top: 200px;
  font-size: 100px;
  height: 500px;
  cursor: pointer;
}
.noselect {
  -webkit-touch-callout: none; /* iOS Safari */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
  user-select: none; /* Non-prefixed version, currently
                                  supported by Chrome and Opera */
}
</style>
