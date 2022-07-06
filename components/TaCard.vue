<template>
  <div class="ta-card my-4">
    <v-card class="totalCard">
      <v-card-title class="ta-card-title">
        <v-icon size="32" style="color: white; margin-top: -20px">{{
          icon
        }}</v-icon>
        <p class="headline mx-2">{{ title }}</p>
      </v-card-title>
      <v-card-text class="ta-card-text">
        <div class="ta-card-text-container mt-2">
          <slot />
        </div>
      </v-card-text>
    </v-card>
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
  },
}
</script>

<style scoped>
.ta-card-title {
  background-color: black;
  color: white;
  height: 70px;
}
.totalCard {
  border: solid black 4px;
}
</style>
