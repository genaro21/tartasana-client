<template>
  <div class="ta-card my-4 mb-12">
    <div class="totalCard">
      <v-card-title class="ta-card-title">
        <v-icon size="32" style="color: black; margin-top: -20px">{{
          icon
        }}</v-icon>
        <p class="headline mx-2 font">{{ title }}</p>
      </v-card-title>
      <v-card-text class="ta-card-text">
        <div class="ta-card-text-container mt-2">
          <slot />
        </div>
      </v-card-text>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
    },
    icon: {
      type: String,
    },
    admin: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style scoped>
.ta-card-title {
  color: fuchsia;
  height: 70px;
  background-color: rgba(200, 200, 200, 0.5);
}
.totalCard {
  border: none;
}
.font {
  font-family: 'Lobster', cursive !important;
}
</style>
