<template>
  <div class="ta-popular">
    <TaCard title="Las + populares" icon="mdi-heart-plus">
      <div class="ta-image-container">
        <v-row>
          <v-col
            cols="6"
            v-for="image in images"
            :key="image.id"
            class="ta-image-container-item"
          >
            <v-img :src="image.url"></v-img>
          </v-col>
        </v-row>
      </div>
    </TaCard>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        {
          id: 1,
          url: 'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/278770501_1298467923974228_7512236160106040911_n.jpg?stp=c0.23.206.206a_dst-jpg_p206x206&_nc_cat=104&ccb=1-7&_nc_sid=da31f3&_nc_ohc=f9UppOtslWwAX_PTfFJ&_nc_oc=AQmEgAqHwhD1f0oT8jXld8niVLnWlZmcitlADv_SGrn-iR2wIWb2JZm4l3rAbGPT-vo&_nc_ht=scontent.fmad19-1.fna&oh=00_AT9Jqw3bkSDBySKiolsa8-3EwsitZOG_lvDOVrRQhOClUw&oe=62D89F0A',
        },
        {
          id: 2,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278974307_1298467887307565_6364941693048755166_n.jpg?stp=c0.23.206.206a_dst-jpg_p206x206&_nc_cat=105&ccb=1-7&_nc_sid=da31f3&_nc_ohc=EizG4OywUwMAX9pvIUW&_nc_ht=scontent.fmad19-2.fna&oh=00_AT9ZxBZYTLobiz0xGsScokaLQN8ROnlI7uSPMJjV8uwvug&oe=62D8CC85',
        },
        {
          id: 3,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278612665_1298467393974281_6307594921332967264_n.jpg?stp=c0.22.206.206a_dst-jpg_p206x206&_nc_cat=102&ccb=1-7&_nc_sid=da31f3&_nc_ohc=dURf9kQqdbAAX_TdPyW&_nc_ht=scontent.fmad19-2.fna&oh=00_AT-Vupkc8J5pC6VyN5zFozLeSAsVOJLehRylWOHKmm8_QQ&oe=62D78731',
        },
        {
          id: 4,
          url: 'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/278795382_1298467433974277_7431052570504946568_n.jpg?stp=dst-jpg_p206x206&_nc_cat=111&ccb=1-7&_nc_sid=da31f3&_nc_ohc=6oKf1_qU8mIAX-dvq1w&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-1.fna&oh=00_AT9oEjRS_Wyp5Oxb50czlLlzdsGiTCjeHBPKhECmsM0r6g&oe=62D73928',
        },
      ],
    }
  },
}
</script>
