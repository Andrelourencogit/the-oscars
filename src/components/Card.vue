<template lang="pug">
  .container-card( :class="isBig ? '' : 'container-small'" :style="image ? style : ''")
    .infos
      p.title {{title}}
      p.year {{year}}
      .links
        DropdownCard.trailer(msg="Trailer")
        DropdownCard(:msg="text")
</template>
<script>
import DropdownCard from '@/components/DropdownCard.vue'

export default {
  name: 'Card',
  components: {
    DropdownCard
  },
  data() {
    return {
      text: 'Assistir',
      src: require('../assets/images/mulan.png')
    }
  },
  props: {
    image: String,
    title: String,
    year: String,
    isBig: Boolean,
    infoDropdown: Array
  },
  computed: {
    style() {
      return (
        `background-image: url(${this.image}); ` +
        `background-position: bottom; ` +
        `background-size: cover;` +
        `border: none;` +
        `background-repeat: no-repeat;`
      )
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

.container-card {
  width: 24.813rem;
  height: 32.875rem;
  border-radius: 8px;
  display: flex;
  align-items: flex-end;
  margin-bottom: 2rem;
  @media (max-width: 992px) {
    width: 100%;
  }


  .infos {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0 1.5rem;

    p {
      font-family: 'Montserrat', sans-serif;
      color: #ffffff;
      margin: 0;
    }

    .title {
      font-weight: bold;
    }

    .year {
      opacity: 60%;
    }

    .links {
      display: flex;

      .trailer {
        pointer-events: none;

        .dropdown-toggle::after {
          display: none;
        }
      }
    }
  }
}

.container-small {
  height: 23.375rem;
}
</style>
