<script>

import menu from '../data/socialLinks'

export default {
  name: 'AppFooter',
  data(){
    return{
      menu
    }
  },
  methods:{
    getImage(imageName) {
      return new URL(`../assets/img/${imageName}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <footer>
    <div class="footer-top">
      <div class="container cols">
        <div class="links">
          <h4>DC Comics</h4>
          <nav>
            <ul>
              <li><a href="#">Characters</a></li>
              <li><a href="#">Comics</a></li>
              <li><a href="#">Movies</a></li>
              <li><a href="#">TV</a></li>
              <li><a href="#">Games</a></li>
              <li><a href="#">Videos</a></li>
              <li><a href="#">News</a></li>
            </ul>
          </nav>
        </div>
        <div class="links">
          <h4>Shop</h4>
          <nav>
            <ul>
              <li><a href="#">Shop DC</a></li>
              <li><a href="#">Shop DC Collectibles</a></li>
            </ul>
          </nav>
        </div>
        <div class="links">
          <h4>DC</h4>
          <nav>
            <ul>
              <li><a href="#">Terms of use</a></li>
              <li><a href="#">Privacy policy (New)</a></li>
              <li><a href="#">Ad Choices</a></li>
              <li><a href="#">Advertising</a></li>
              <li><a href="#">Jobs</a></li>
              <li><a href="#">Subscriptions</a></li>
              <li><a href="#">Talent Workshops</a></li>
              <li><a href="#">CPSC certificates</a></li>
              <li><a href="#">Raings</a></li>
              <li><a href="#">Shop help</a></li>
              <li><a href="#">Contact us</a></li>
            </ul>
          </nav>
        </div>
        <div class="links">
          <h4>Sites</h4>
          <nav>
            <ul>
              <li><a href="#">DC</a></li>
              <li><a href="#">MAD Magazine</a></li>
              <li><a href="#">DC Kids</a></li>
              <li><a href="#">DC Universe</a></li>
              <li><a href="#">DC Power Visa</a></li>
            </ul>
          </nav>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="container">
        <a class="button" href="#">Sign up now!</a>
        <nav>
          <h4>follow us</h4>
          <ul>
            <li v-for="(icon, index) in menu" :key="index">
              <a :href="icon.href">
                <img :src="getImage(icon.iconName)" :alt="icon.text">
              </a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>

@use '../styles/partials/mixin' as *;
@use '../styles/partials/variables' as *;

footer {

  .footer-top {
    background-image: url('../assets/img/footer-bg.jpg');
    background-size: cover;
    height: 370px;
    overflow: hidden;
    .cols{
      @include flexCol;
      padding: 1rem 0;
      background-image: url("../assets/img/dc-logo-bg.png");
      background-position: right;
      background-repeat: no-repeat;
      height: 100%;
      flex-wrap: wrap;
      align-content: flex-start;
      .links {
        margin-right: 30px;
        h4 {
          text-transform: uppercase;
          color: white;
          font-size: 1.2rem;
          margin: 1rem 0;
        }
        ul {
          li {
            a {
              color: rgba(255, 255, 255, 0.4);
              text-transform: capitalize;
              &:hover {
                color: white;
              }
            }
          }
        }
      }
    }
}
  .footer-bottom {
    height: 110px;
    background-color: #303030;
    .container {
      @include spaceBetween;
      align-items: center;
      height: 100%;
      a.button {
        color: white;
        text-transform: uppercase;
        display: inline-block;
        border: 2px solid $primary-color;
        padding: 6px 10px;
        &:hover {
          background-color: $primary-color;
          border-color: white;
        }
      }
      nav {
        @include centerFlex('horizontal');
        h4 {
          margin: 0 10px;
          text-transform: uppercase;
          color: $primary-color;
          line-height: 36px;
        }
        ul {
          display: flex;
          li {
            margin-left: 1rem;
            a {
              &:hover {
                filter: brightness(1.5);
              }
              img {
                width: 36px;
              }
            }
          }
        }
      }
    }
  } 
}

</style>