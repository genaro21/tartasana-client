<template>
  <div class="ta-tradicionales">
    <TaCard title="Tradicionales" icon="mdi-kettle-pour-over">
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
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278776276_1298467950640892_3146555375139244250_n.jpg?stp=c0.23.206.206a_dst-jpg_p206x206&_nc_cat=100&ccb=1-7&_nc_sid=da31f3&_nc_ohc=cv_t32Fy7lsAX9auhUb&_nc_ht=scontent.fmad19-2.fna&oh=00_AT_TRsFhGsSEoS0v7cZhu8uKgI7Bam8_i2AKclM2rm4Q8Q&oe=62D86848',
        },
        {
          id: 2,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/279456173_1298468100640877_523785307781830463_n.jpg?stp=c34.0.206.206a_dst-jpg_p206x206&_nc_cat=101&ccb=1-7&_nc_sid=da31f3&_nc_ohc=JXe7V89im2sAX_gZsuK&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-2.fna&oh=00_AT_xi_oFSS_WihUsHpVz7I5t4ndcX40SqATWk195OCLa3Q&oe=62D881F4',
        },
        {
          id: 3,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278575117_1298468183974202_5815977826917725726_n.jpg?stp=c0.23.206.206a_dst-jpg_p206x206&_nc_cat=102&ccb=1-7&_nc_sid=da31f3&_nc_ohc=lYHyByvZa5AAX-T2mAE&_nc_ht=scontent.fmad19-2.fna&oh=00_AT8ZwC5EoQ0NZcVYahiS_kt1B_LGIL5z6H-fneyL3RhduA&oe=62D70435',
        },
        {
          id: 4,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/287944741_1328492850971735_8917616907706442536_n.jpg?stp=c0.22.206.206a_dst-jpg_p206x206&_nc_cat=101&ccb=1-7&_nc_sid=da31f3&_nc_ohc=VPZgSuOE6OYAX-OEqOo&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-2.fna&oh=00_AT84VMB3zlGUADFMdPJAqNROr5iW9KF4_YATHv_nzPu8zA&oe=62D7076D',
        },
      ],
    }
  },
}
</script>
