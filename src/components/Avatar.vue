<template>
  <div class="avatar">
    <img
      :src="require(`../assets/image-${imageName}.jpg`)"
      class="avatar__img"
      alt="profile image"
      :class="{ 'inverse-border': border }"
    />
    <div class="avatar__profile-group">
      <h3 class="name avatar__name" :class="{ 'inverse-name': inverse }">
        {{ name }}
      </h3>
      <p class="body avatar__body">{{ account }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Avatar",
  props: {
    imageName: String,
    name: String,
    account: String,
    inverse: Boolean,
    border: Boolean,
  },
  data() {
    return {
      url: "../assets/image-daniel.jpg",
      // image: require(`${this.profileImage}`),
      image_test: require("../assets/image-daniel.jpg"),
    };
  },
  computed: {},
  created() {
    console.log(this.imageName);
  },
};
</script>

<style lang="scss" scoped>
.avatar {
  display: flex;
  margin-bottom: 18px;

  &__img {
    display: block;
    border-radius: 50%;
    height: 28px;
    width: 28px;
    margin-right: 17px;
    /* border: 2px solid red; */
  }
}
</style>
