<template>
  <div class="ta-lastest-comments">
    <TaCard title="Comentarios" icon="mdi-message-fast">
      <TaCommentItem
        v-for="comment in comments"
        :key="comment.id"
        :image="comment.image"
        :email="comment.email"
        :comment="comment.comment"
      />
    </TaCard>
  </div>
</template>

<script>
export default {
  data() {
    return {
      comments: [
        {
          id: 1,
          image:
            'https://scontent.fmad19-1.fna.fbcdn.net/v/t39.30808-6/289272989_1334021593752194_5363424679314490526_n.jpg?stp=dst-jpg_p526x296&_nc_cat=111&ccb=1-7&_nc_sid=730e14&_nc_ohc=AORzr3LmWMAAX-StPyq&tn=0SGYRnQYef9bVxlp&_nc_ht=scontent.fmad19-1.fna&oh=00_AT9ZeXT16rc_w1DIBOfY1VLbDHA9jJOdoZ7H8-VvVxXTag&oe=62C3BB81',
          email: 'pepe@gmail.com',
          comment:
            'descripcion 1 sñadfjkhsñdjkfgnskdjfcgnñskjdfgnksjdfxbcgjvsdhfgksvjdxnñcvkjsdfkxgj',
        },
        {
          id: 2,
          image:
            'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278575117_1298468183974202_5815977826917725726_n.jpg?_nc_cat=102&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=zNSNCltTJcAAX_yXDfL&_nc_ht=scontent.fmad19-2.fna&oh=00_AT8xTNfKbWEXTbvX--tRuIzk2TNIbG6DHPJz4amqGocKHg&oe=62C537F5',
          email: 'jose@gmail.com',
          comment:
            'decripcion 2 sñadfjkhsñdjkfgnskdjfcgnñskjdfgnksjdfxbcgjvsdhfgksvjdxnñcvkjsdfkxgj',
        },
        {
          id: 3,
          image:
            'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/279272793_1298468160640871_8368903707378243051_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=Do30MYl6en8AX8oD59M&_nc_ht=scontent.fmad19-2.fna&oh=00_AT9CDn6CwyuWoKMX9kKcXGOMxqP_0crJv4NfqSN1yTLsVA&oe=62C4AC93',
          email: 'juan@gmail.com',
          comment:
            'descripcion 3 sñadfjkhsñdjkfgnskdjfcgnñskjdfgnksjdfxbcgjvsdhfgksvjdxnñcvkjsdfkxgj',
        },
        {
          id: 4,
          image:
            'https://scontent.fmad19-2.fna.fbcdn.net/v/t39.30808-6/278584621_1298468127307541_804690123460261316_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=ZWEOzH9Y1AMAX9szien&_nc_ht=scontent.fmad19-2.fna&oh=00_AT8mlXufvgbfYbCWCH5VjGsbdjJELV27e8_eHVrpWetk4g&oe=62C40EEB',
          email: 'kiko@gmail.com',
          comment:
            'descripcion 4 sñadfjkhsñdjkfgnskdjfcgnñskjdfgnksjdfxbcgjvsdhfgksvjdxnñcvkjsdfkxgj',
        },
      ],
    }
  },
}
</script>
