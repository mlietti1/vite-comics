<script>
export default {

}
</script>

<template>
  <footer>
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
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
          </ul>
        </nav>
      </div>
      <div class="links">
        <h4>Sites</h4>
        <nav>
          <ul>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
            <li><a href="#"></a></li>
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
  background-image: url('../assets/img/footer-bg.jpg');
  height: 370px;
  padding: 10px 0;
  .cols{
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    .links {
      h4 {
        text-transform: uppercase;
        color: white;
        font-size: 1.2rem;
        margin: 20px 0;
      }
      ul {
        list-style: none;
        li {
          a {
            text-decoration: none;
            color: rgba(255, 255, 255, 0.5);
            text-transform: capitalize;
          }
        }
      }
    }
  }
}

</style>