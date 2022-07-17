<template>
  <div class="ta-recent-uploads">
    <TaCard title="Ultimas entradas" icon="mdi-fast-forward">
      <div class="ta-image-container">
        <v-row>
          <v-col
            cols="3"
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
          url: 'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/289024074_1334022080418812_2320714272821502156_n.jpg?stp=dst-jpg_p526x296&_nc_cat=110&ccb=1-7&_nc_sid=730e14&_nc_ohc=IQa_WpgnAPcAX9kO7Gu&_nc_ht=scontent.fmad19-1.fna&oh=00_AT-F1gvTO_z473f1MF8UJjZfnPVMaOYzyCpNeBnFpQSIKQ&oe=62C40BCF',
        },
        {
          id: 2,
          url: 'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/279035058_1298467910640896_838629800379788031_n.jpg?stp=c0.23.206.206a_dst-jpg_p206x206&_nc_cat=104&ccb=1-7&_nc_sid=da31f3&_nc_ohc=CmPA2zxcuIEAX-tMErk&_nc_ht=scontent.fmad19-1.fna&oh=00_AT_hmAnQmyOKDuplbHkHM9vKHifLqwQKoNvNcGNf9sfXRQ&oe=62D8E928',
        },
        {
          id: 3,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278578228_1298467700640917_5295786508426667952_n.jpg?stp=c34.0.206.206a_dst-jpg_p206x206&_nc_cat=106&ccb=1-7&_nc_sid=da31f3&_nc_ohc=Uv4zaEEYI5YAX-Vsat5&_nc_ht=scontent.fmad19-2.fna&oh=00_AT8LIg2c3vKkSh5Y04HKoBFYffsWl4LU46d_q2xfJb0Txw&oe=62D7D6A8',
        },
        {
          id: 4,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/279413289_1298468063974214_1169787687256187782_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=fE8KL62YkXwAX9Azd0w&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-2.fna&oh=00_AT-pddFocbLab4Liri6yhwWYPfIVrbIeIMsKQYvMLZpXcg&oe=62C4DCAC',
        },
        {
          id: 5,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278776276_1298467950640892_3146555375139244250_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=86JVWJ3G2ZYAX9-f6B4&_nc_ht=scontent.fmad19-2.fna&oh=00_AT8m2LMjH6jnekmt_BJaVjtQWdIKlbZuWo10zB7TxRMtuA&oe=62C4A1C8',
        },
        {
          id: 6,
          url: 'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/278770501_1298467923974228_7512236160106040911_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=iUScgQyWg-4AX_pvjPR&_nc_oc=AQnrW3_8lJSqfEgI28tum_92kICTrC5Ku55-6H8LBfWqP-WHfyWjp9ENGmbOsjsS6jk&_nc_ht=scontent.fmad19-1.fna&oh=00_AT9r6JQvcT_LALSVGeou5ATcL8GsixhYNzfjGihkPWFovA&oe=62C4D88A',
        },
        {
          id: 7,
          url: 'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/279035058_1298467910640896_838629800379788031_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=4crXaaNHN6AAX-BpUDM&_nc_ht=scontent.fmad19-1.fna&oh=00_AT_o_uByrkx_KxEgJLcQDXopj7CQ97IJBAF1av8ggI8QbA&oe=62C522A8',
        },
        {
          id: 8,
          url: 'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278902935_1298467487307605_5557510444425587522_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=u78QBX6ZtFYAX_de3n4&_nc_ht=scontent.fmad19-2.fna&oh=00_AT8hyy92N7JgtrQ3eFcq6ZwBQpmDD8FYBWOg6yPsrVMQww&oe=62C5441D',
        },
      ],
    }
  },
}
</script>
