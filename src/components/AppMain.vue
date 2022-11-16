<script>

import menu from '../data/buyLinks';
import cards from '../data/cardsData';
import AppCard from './AppCard.vue';

export default {
  name: 'AppMain',
  components: {
    AppCard
  },
  data(){
    return{
      cards,
      menu
    }
  }
}
</script>

<template>
  <main>
    <div class="jumbo">
    </div>
    <div class="content container">
      <h2 class="content-title">Current series</h2>
      <div class="cards-row">
        <AppCard v-for="(item, index) in cards" :key="index" :card="item" />
      </div>
      <div class="btn-row"><a class="btn-load" href="#">load more</a></div>
    </div>
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
  .jumbo {
    background-image: url('../assets/img/jumbotron.jpg');
    height: 400px;
    background-size: cover;
  }
  .content {
    position: relative;
    padding: 20px 0;
    .content-title {
      position: absolute;
      left: 0;
      top: 0;
      transform: translateY(-50%);
      text-transform: uppercase;
      background-color: $primary-color;
      padding: 8px 20px;
    }
    .cards-row {
      @include centerFlex('horizontal');
      flex-wrap: wrap;
      margin: 20px 0;
    }
    .btn-row {
      width: 100%;
      text-align: center;
      .btn-load {
        text-transform: uppercase;
        display: inline-block;
        padding: 8px 50px;
        background-color: $primary-color;
        color: white;
        font-weight: 700;
      }
    }
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
      justify-content: space-around;
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