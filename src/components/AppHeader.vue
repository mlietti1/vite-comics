<script>
export default {
  name: 'AppHeader',
  data(){
    return{
      menu: [
        {
          text:'Characters',
          href: '#',
          current: false
        },
        {
          text:'Comics',
          href: '#',
          current: true
        },
        {
          text:'Movies',
          href: '#',
          current: false
        },
        {
          text:'TV',
          href: '#',
          current: false
        },
        {
          text:'Games',
          href: '#',
          current: false
        },
        {
          text:'Collectibles',
          href: '#',
          current: false
        },
        {
          text:'Videos',
          href: '#',
          current: false
        },
        {
          text:'Fans',
          href: '#',
          current: false
        },
        {
          text:'News',
          href: '#',
          current: false
        },
        {
          text:'Shop',
          href: '#',
          current: false
        }
      ]
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
        list-style: none;
        text-transform: uppercase;
        li {
          margin: 0 1rem;
          a {
            text-decoration: none;
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