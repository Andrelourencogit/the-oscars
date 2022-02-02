<template lang="pug">
  .container-options
    b-dropdown#dropdown-right.m-2(right='' :text='msg' variant='primary')
      .content(v-for='(info, index) in infoDropdown')
        .info-1
          img(:src='info.src')
          p {{info.name}}
        .info-2
          p {{info.description}}
</template>
<script>
export default {
  name: 'Dropdown',
  props: {
    msg: String,
    description: String,
    name: String,
    options: Array
  },
  data() {
    return {
      text: 'Assistir',
      src: require('../assets/images/mulan.png'),
      infoDropdown: [
        {
          name: 'Netflix',
          src: require('../assets/images/netflix.png'),
          description: 'Assinatura'
        },
        {
          name: 'Youtube',
          src: require('../assets/images/youtube.png'),
          description: 'A partir de R$ 14,90'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.container-options {
  display: flex;
  justify-content: flex-end;
  width: 100%;
  font-family: 'Montserrat', sans-serif;

  .content {
    display: flex;
    justify-content: space-between;
    margin-bottom: 15px;
    &:last-child {
      margin-bottom: 0;
    }

    .info-1,
    .info-2 {
      p {
        color: #13171D;
        font-size: 14px;
      }
    }

    .info-1 {
      display: flex;
      p {
        font-weight: bold;
      }
    }

    .info-2 {
      p {
        font-style: italic;
      }
    }
    
  }

  .btn-group > .btn,
  .btn-group-vertical > .btn {
    background: #13171D 0% 0% no-repeat padding-box !important;
    box-shadow: 0px 5px 6px #00000029 !important;
    border-radius: 26px !important;
    opacity: 1 !important;
    border: none;
    padding: 0.625rem 1.875rem;
  }

  .dropdown-menu.show {
    border-radius: 15px;
    min-width: 280px;
    padding: 15px;

    li {
      padding: 0.25rem 1rem;
      &:hover,
      &:focus {
        background-color: #0d316765;
        .dropdown-item,
        .dropdown-item {
          color: #ffffff;
        }
      }
      a {
        border-bottom: 1px solid #13171d0d;
        padding: 0;
        pointer-events: none;
      }
    }
  }

  .dropdown-menu.show {
    margin-top: 8px;
  }
}
</style>
