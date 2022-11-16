<script>
export default {
  name: 'AppMain',
  data(){
    return{
      menu: [
        {
          imgPath: '/src/assets/img/buy-comics-digital-comics.png',
          text: 'digital comics',
          href: '#'
        },
        {
          imgPath: '/src/assets/img/buy-comics-merchandise.png',
          text: 'dc merchandise',
          href: '#'
        },
        {
          imgPath: '/src/assets/img/buy-comics-subscriptions.png',
          text: 'subscription',
          href: '#'
        },
        {
          imgPath: '/src/assets/img/buy-comics-shop-locator.png',
          text: 'comic shop locator',
          href: '#'
        },
        {
          imgPath: '/src/assets/img/buy-dc-power-visa.svg',
          text: 'dc power visa',
          href: '#'
        }
      ]
    }
  }
}
</script>

<template>
  <main>
    <div class="content container">Content</div>
    <div class="buy">
      <div class="container">
        <nav>
          <ul>
            <li v-for="(link, index) in menu" :key="index">
              <a :href="link.href">
                <img :src="link.imgPath" :alt="link.text">
                {{link.text}}
              </a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variables' as *;

main {
  .content {
    padding: 30px 0;
  }
  background-color: #1c1c1c;
  color: white;
  .buy{
    @include centerFlex('vertical');
    background-color: $primary-color;
    color: white;
    height: 155px;
    ul {
      display: flex;
      justify-content: space-evenly;
      list-style: none;
      li {
        &:last-of-type img{
          height: 35px;
        }
        a {
          color: white;
          text-decoration: none;
          text-transform: uppercase;
          line-height: 55px;
          &:hover {
            color: #1c1c1c;
          }
          img {
            vertical-align: middle;
            height: 55px;
            margin-right: 10px;
          }
        }
      }
    }
  }
}

</style>