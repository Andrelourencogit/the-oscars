<template lang="pug">
  .home
    img(alt='Vue logo' src='../assets/images/Logo-Oscars.svg')
    Dropdown(:msg="infoDropdown.text" :options="infoDropdown.info")
    .container
        .content-1
          template(v-for='(info, index) in infoCard')
            Card(v-if="index%2 == 0" :title='info.title' :year='info.infoYear' :isBig="info.isBig" :image="info.src")
        .content-2
          template(v-for='(info, index) in infoCard')
            Card(v-if="index%2 != 0" :title='info.title' :year='info.infoYear' :isBig="info.isBig" :image="info.src")
</template>

<script>
// @ is an alias to /src
import Dropdown from '@/components/Dropdown.vue'
import Card from '@/components/Card.vue'

export default {
  name: 'Home',
  components: {
    Dropdown,
    Card
  },
  data() {
    return {
      infoDropdown: {
        text: 'Filtrar por',
        info: [
          { label: 'Ordem alfabética' },
          { label: 'Score do IMDB' },
          { label: 'Duração' },
          { label: 'Número de indicações' }
        ]
      },
      infoCard: [
        {
          title: 'Mulan',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/mulan.png'),
          isBig: true
        },
        {
          title: 'Over the Moon',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/moon.png'),
          isBig: false
        },
        {
          title: 'Bacurau',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/bacurau.png'),
          isBig: false
        },
        {
          title: 'The Midnight Sky',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/ceu.png'),
          isBig: true
        },
        {
          title: 'Love And Monters',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/love.png'),
          isBig: true
        },
        {
          title: 'Another Round',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/another.png'),
          isBig: false
        },
        {
          title: 'Emma',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/emma.png'),
          isBig: false
        },
        {
          title: 'The Trial',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/chicago.png'),
          isBig: true
        },
        {
          title: 'Enet',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/net.png'),
          isBig: true
        },
        {
          title: 'Fence',
          infoYear: '2h20m • 2020',
          src: require('../assets/images/fences.png'),
          isBig: false
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.home {
  display: flex;
  flex-direction: column;
  align-items: center;

  @media (max-width: 768px) {
    img {
      width: 90%;
      padding: 0.625rem;
      margin-top: 40px;
    }
  }

  .container {
    display: flex;
    justify-content: space-around;

    .content-1,
    .content-2 {
      display: flex;
      width: 40%;
      flex-direction: column;
      // flex-wrap: wrap;
      // justify-content: space-around;
    }
  }
}
</style>
