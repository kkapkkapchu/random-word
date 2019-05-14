<template>
  <div class="root">
    <div class="cardWrapper">
      <Card
        v-for="item in items"
        :key="item.key"
        :data="item"
        @click="onClickCard"
      />
    </div>
    <ShowWord
      v-if="showValues.length"
      :data="showValues"
    />
  </div>
</template>

<script>
import Card from "./Card";
import ShowWord from "./ShowWord";

export default {
  name: "RandomWord",
  components: {
    Card,
    ShowWord
  },
  data() {
    return {
      items: [
        {
          key: "1",
          value: ["aaa1", "bbb1", "ccc1", "ddd1", "eee1"]
        },
        {
          key: "2",
          value: ["aaa2", "bbb2", "ccc2", "ddd2", "eee2"]
        },
        {
          key: "3",
          value: ["aaa3", "bbb3", "ccc3", "ddd3", "eee3"]
        },
        {
          key: "4",
          value: ["aaa4", "bbb4", "ccc4", "ddd4", "eee4"]
        }
      ],
      showValues: []
    };
  },
  methods: {
    onClickCard(value) {
      this.showValues = value;
    }
  }
};
</script>

<style scoped>
.cardWrapper {
  display: flex;
  justify-content: center;
}
</style>
