<template>
  <div
    v-for="(item, index) in content"
    :key="index"
    :class="item.styles.class_name"
    class="card"
  >
    <img
      class="card__bg-image"
      v-if="item.styles.bg_image"
      :src="require(`../assets/${item.styles.bg_image}.svg`)"
      alt="qoutation-mark"
    />
    <Avatar
      :imageName="item.avatar.image_name"
      :name="item.avatar.name"
      :account="item.avatar.account"
      :inverse="item.styles.inverse_text"
      :border="item.styles.border_avatar"
    />
    <h1
      class="headline"
      :class="{ 'inverse-headline': item.styles.inverse_text }"
    >
      {{ item.headline }}
    </h1>
    <p class="body" :class="{ 'inverse-body': item.styles.inverse_text }">
      {{ item.body }}
    </p>
  </div>
</template>

<script>
import Avatar from "./Avatar.vue";

export default {
  name: "Card",
  components: {
    Avatar,
  },
  props: {
    content: Object,
  },
  data() {
    return {
      styleObject: {
        fontSize: "13px",
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.card {
  position: relative;
  border-radius: 8px;
  padding: 26px 32px 32px;
  box-shadow: rgba(17, 17, 26, 0.05) 0px 4px 16px,
    rgba(17, 17, 26, 0.05) 0px 8px 32px;

  &__bg-image {
    position: absolute;
    width: 104px;
    height: 102px;
    left: 369px;
    top: 1px;
    z-index: 1;
  }
}

/**
* Dynamic card styles
*/
.card-1 {
  background-color: $COLOR_PURPLE;
  grid-area: card-1;
}

.card-2 {
  background-color: $COLOR_GREY;
  grid-area: card-2;
}

.card-3 {
  background-color: $COLOR_WHITE;
  grid-area: card-3;
  /* padding-bottom: 26px; */
}

.card-4 {
  background-color: $COLOR_WHITE;
  grid-area: card-4;
  padding-bottom: 26px;
}
.card-5 {
  background-color: $COLOR_DARK_BLUE;
  grid-area: card-5;
  padding-bottom: 26px;
}
</style>
