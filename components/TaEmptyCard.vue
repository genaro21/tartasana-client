<template>
  <div class="ta-emptyCard">
    <v-card>
      <v-card-text class="ta-card-text">
        <div class="ta-card-text-container mt-2">
          <slot />
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<style scoped>
.ta-emptyCard {
  border: solid black 4px;
}
</style>
