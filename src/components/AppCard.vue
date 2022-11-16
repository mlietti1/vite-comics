<script>

export default {
  name: 'Card',
  props: {
    card: Object
  }
}
</script>

<template>
  <div class="card">
    <div class="card-img">
      <img :src="card.thumb" alt="card.series">
    </div>
    <span>{{card.series}}</span>
    <span class="price">{{card.price}}</span>
  </div>
</template>

<style lang="scss" scoped>

@use '../styles/partials/variables' as *;
@use '../styles/partials/mixin' as *;

.card {
  width: 185px;
  margin: 15px;
  cursor: pointer;
  position: relative;
  &:hover .card-img{
    filter: brightness(.5);
  }
  &:hover .price {
    opacity: 100%;
  }
  .card-img {
    width: 100%;
    height: 185px;
    overflow: hidden;
    margin-bottom: 10px;
  }
  span {
    text-transform: uppercase;
  }
  .price {
    position: absolute;
    right: 0;
    top: 15px;
    display: inline-block;
    opacity: 0%;
    padding: 4px 12px;
    background-color: red;
    transition: all 0.6s;
  }
}

</style>