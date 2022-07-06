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
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/287944741_1328492850971735_8917616907706442536_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=l2U7HDw4CCkAX9EIUzz&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-2.fna&oh=00_AT8YW_GXevxdSt7x_XyRfNfltSC_NZoY2d0KTkcFp3DhsA&oe=62C53B2D',
        },
        {
          id: 2,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/279456173_1298468100640877_523785307781830463_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=Mj1iboZIh1MAX8GO097&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-2.fna&oh=00_AT88-EMQp5E3nIN0yj7vcrgTqXjcQ-tr4UYCUzq-HGVPfA&oe=62C4BB74',
        },
        {
          id: 3,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278579324_1298467790640908_324676771172617374_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=263hq0zQx_gAX8_mR2o&_nc_ht=scontent.fmad19-2.fna&oh=00_AT_nqhhTJIEp-0sCikafnXCUrQJYuJmZJ-3ukf6uf2YO4w&oe=62C64D7D',
        },
        {
          id: 4,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/279155492_1298467623974258_8924275418808758875_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=8JNrjnlpuqAAX-H0PsA&_nc_ht=scontent.fmad19-2.fna&oh=00_AT-ArthxNoMHWOsFUmzMfDMuoWAkCS1-7lvF1AKwhNaVkw&oe=62C67609',
        },
      ],
    }
  },
}
</script>
