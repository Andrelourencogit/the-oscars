<template lang="pug">
  .container-options
    b-dropdown#dropdown-right.m-2(right='' :text='msg' variant='primary')
      b-dropdown-item(href='#' v-for='(info, index) in options' :key="index") {{info.label}}
</template>
<script>
export default {
  name: 'Dropdown',
  props: {
    msg: String,
    options: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.container-options {
  display: flex;
  justify-content: flex-end;
  width: 100%;

  .btn-group > .btn,
  .btn-group-vertical > .btn {
    background: #ffffff1a 0% 0% no-repeat padding-box !important;
    box-shadow: 0px 5px 6px #00000029 !important;
    border-radius: 26px !important;
    opacity: 1 !important;
    border: none;
  }

  .dropdown-menu.show {
    border-radius: 15px;

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
