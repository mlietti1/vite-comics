<script>

import menu from '../data/headerLinks'

export default {
  name: 'AppHeader',
  data(){
    return{
      menu
    }
  }
}
</script>

<template>
  <header>
    <div class="container">
      <div class="logo">
        <img src="/dc-logo.png" alt="">
      </div>
      <nav>
        <ul>
          <li
          v-for="(link, index) in menu"
          :key="index">
            <a :class="{'active': link.current}" :href="link.href">{{link.text}}</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>

@use '../styles/partials/mixin' as *;
@use '../styles/partials/variables' as *;

header {
  .container {
    @include spaceBetween;
    .logo {
    @include centerFlex('vertical');
      img {
      width: 80px;
      }
    }

    nav {
      ul {
        @include centerFlex('vertical');
        text-transform: uppercase;
        li {
          margin: 0 1rem;
          a {
            display: inline-block;
            color: black;
            padding: 3rem 0;
            border-bottom: 5px solid transparent;
            &:hover {
              color: $primary-color;
              border-bottom: 5px solid $primary-color;
            }
            &.active{
              border-bottom: 5px solid $primary-color;
            }
          }
        } 
      }
    }
  }

}

</style>