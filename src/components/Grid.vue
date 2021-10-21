<template>
  <div class="grid">
    <Card :content="fetchContent()" />
  </div>
</template>

<script>
import content from "../assets/content/content.json";
import Card from "./Card.vue";

export default {
  name: "Grid",
  components: {
    Card,
  },
  props: {},
  methods: {
    fetchContent() {
      return content[0];
    },
  },
};
</script>

<style lang="scss" scoped>
.grid {
  display: flex;
  flex-direction: column;
  align-items: center;
  row-gap: 24px;
  width: 327px;
  min-height: 1824px;
  margin: 0 auto;

  @include mq($from: desktop) {
    display: grid;
    grid-template-columns: repeat(4, 255px);
    grid-template-rows: 282px 266px;
    column-gap: 30px;
    row-gap: 24px;
    grid-template-areas:
      "card-1 card-1 card-2 card-3"
      "card-4 card-5 card-5 card-3";

    min-width: 1110px;
    min-height: 572px;
  }
}
</style>
