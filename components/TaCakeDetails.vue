<template>
  <div class="ta-cake-details">
    <TaCard :title="title" icon="mdi-heath">
      <div class="ta-image-details-container">
        <v-img
          height="400px"
          src="https://scontent.fmad19-2.fna.fbcdn.net/v/t1.6435-9/71765472_666996037121423_1282604979797884928_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=fTQgaxtLT7oAX-CFaE_&_nc_ht=scontent.fmad19-2.fna&oh=00_AT8ASKwUUg2ZndIdkZwHcmgZv6tEash2dLSsgSAxICUL4g&oe=62E8BA69"
        />
        <div class="ta-image-details-container-description mt-4">
          <p class="headline font-weight-black">{{ title }}</p>
          <p>{{ description }}</p>
        </div>
        <div class="ta-image-details-container-icon d-flex">
          <div class="d-flex justify-start">
            <v-btn color="success">
              <v-icon class="mr-2">mdi-thumb-up</v-icon>
              Like
            </v-btn>
            <div class="mx-12">
              <v-icon class="d-flex justify-center">mdi-cards-heart</v-icon>
              <p>Likes</p>
            </div>
            <div class="mx-12">
              <v-icon class="d-flex justify-center">mdi-eye-settings</v-icon>
              <p>Views</p>
            </div>
          </div>

          <v-spacer></v-spacer>
          <div class="mr-6 my-2"><p>12/05/2021</p></div>
        </div>
      </div>
    </TaCard>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Nombre de la tarta',
      description:
        'adñfgajdñfa vd-fkb kjasbdñgkjadhkjvbajdk añksdjfhñaskjdbvñkhsbv ákadgféaklnjn ´ksjfgkñjsdnf´kan skdfjgsdkjfbnskdjfh',
    }
  },
}
</script>
