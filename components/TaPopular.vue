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
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278897944_1298467817307572_909682412130278560_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=C4Kunxdzp9cAX9iHZg7&_nc_ht=scontent.fmad19-2.fna&oh=00_AT-U3VMyAHQ_YZ9O6yJzHunGEF0nFx7qlC5zYHpWzpgkBA&oe=62C4269D',
        },
        {
          id: 2,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/279449197_1298467767307577_4929802263684004826_n.jpg?_nc_cat=102&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=3HwfO9wEjr0AX_tqaOH&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-2.fna&oh=00_AT-Wr0PhROW0ARj2o4q5jupPwBhgDn8rF7UiRVqqLKiSXw&oe=62C418D5',
        },
        {
          id: 3,
          url: 'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/279100842_1298467560640931_7697580503491682796_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=0NtIFQGOKSIAX9WZ3Zj&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-1.fna&oh=00_AT9cMbt8fMtS89a2tqYb5nct0b3bPueE_kBBaDBi0hTcpA&oe=62C2C6D5',
        },
        {
          id: 4,
          url: 'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/278681305_1298468220640865_2340320219670416409_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=3UWyuNIAaScAX_pKwQG&_nc_ht=scontent.fmad19-1.fna&oh=00_AT8ENOfq_sL7XOTh1P9BiEsD-kk9_t0lnegxtncTtZ-RSw&oe=62C38429',
        },
      ],
    }
  },
}
</script>
