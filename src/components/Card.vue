<template>
  <div
    class="card"
    @click="onClick"
  >
    {{ data.key }}
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    data: {
      type: Object,
      default: () => {}
    }
  },
  methods: {
    toggleActive(e) {
      const activeElement = document.querySelector(".active");
      if (activeElement) {
        activeElement.classList.remove("active");
      }

      e.target.classList.add("active");
    },
    shuffle(array) {
      let currentIndex = array.length,
        temporaryValue,
        randomIndex;

      // While there remain elements to shuffle...
      while (0 !== currentIndex) {
        // Pick a remaining element...
        randomIndex = Math.floor(Math.random() * currentIndex);
        currentIndex -= 1;

        // And swap it with the current element.
        temporaryValue = array[currentIndex];
        array[currentIndex] = array[randomIndex];
        array[randomIndex] = temporaryValue;
      }

      return array;
    },
    onClick(e) {
      this.toggleActive(e);
      this.$emit("click", this.shuffle(this.data.value));
    }
  }
};
</script>

<style scoped>
.card {
  width: 200px;
  height: 100px;
  border: 1px solid #dedede;
  border-radius: 5px;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card.active {
  background: #f39c12;
}
</style>
