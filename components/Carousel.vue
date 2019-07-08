<template lang="pug">
.carousel-wrap
  .carousel-container
    .carousel(:style="{ transform: 'translateX' + '(' + currentOffset + 'px' + ')'}")
      .carousel__item(v-for="item in items")
        img.carousel__img(:src="require(`~/assets/img-` + item.img + `.png`)")
        .carousel__text {{ item.text }}
  .carousel-controls
    .carousel-arrow.carousel-arrow--left(@click="moveCarousel(-1)" :disabled="atHeadOfList")
      img(src="~assets/carousel-arrow.png")
    .carousel-arrow.carousel-arrow--right(@click="moveCarousel(1)" :disabled="atEndOfList")
      img(src="~assets/carousel-arrow.png")
</template>

<script>
import img1 from '~/assets/img-1.png'
import img2 from '~/assets/img-2.png'
import img3 from '~/assets/img-3.png'
import img4 from '~/assets/img-4.png'

export default {
  data() {
    return {
      currentOffset: 0,
      windowSize: 4,
      paginationFactor: 300,
      items: [
        {text: 'Balence transform', img: '1'},
        {text: 'Internet Banking', img: "2"},
        {text: 'Buying Payment', img: "3"},
        {text: 'Buy Air Ticket', img: "4"},
        {text: 'Balence transform', img: "1"},
        {text: 'Internet Banking', img: "2"},
        {text: 'Buying Payment', img: "3"},
        {text: 'Buy Air Ticket', img: "4"}
      ]
    }
  },
  computed: {
    atEndOfList() {
      return this.currentOffset <= (this.paginationFactor * -1) * (this.items.length - this.windowSize);
    },
    atHeadOfList() {
      return this.currentOffset === 0;
    }
  },
  methods: {
    moveCarousel(direction) {
      if (direction === 1 && !this.atEndOfList) {
        this.currentOffset -= this.paginationFactor;
      } else if (direction === -1 && !this.atHeadOfList) {
        this.currentOffset += this.paginationFactor;
      }
    }
  }
}
</script>

<style lang="scss">
.carousel-wrap {
  margin-top: 65px;
  position: relative;
  width: 100%;
  max-width: 270px;
  margin: 0 auto;
  margin-top: 65px;

  @media (min-width: 768px) {
    max-width: 570px;
  }

  @media (min-width: 992px) {
    max-width: 870px;
  }

  @media (min-width: 1200px) {
    max-width: 100%;
  }
}
.carousel-container {
  overflow: hidden;
}
.carousel {
  display: flex;
  transition: transform 150ms ease-out;
  transform: translatex(0);
}
.carousel__item {
  width: 100%;
  // flex: 0 0 calc(100% / 12 * 3);
  // max-width: calc(100% / 12 * 3);
  // flex-shrink: 1;

  &:not(:last-child) {
    margin-right: 30px;
  }
}
.carousel__img {
  display: block;
}
.carousel__text {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 80px;
  border: 1px solid #b3b3b3;
  border-top: none;
  color: #333;
  font-family: "Poppins", sans-serif;
  font-weight: normal;
  font-size: 20px;
}

.carousel-controls {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: none;

  @media (min-width: 1200px) {
    display: block;
  }
}
.carousel-arrow {
  position: absolute;
  top: 50%;
  cursor: pointer;

  &:hover {
    transform: scale(1.1);
  }

  &--left {
    transform: rotate(180deg);
    left: -82px;

    &:hover {
      transform: rotate(180deg) scale(1.1);
    }
  }
  &--right {
    right: -82px;
  }

  &[disabled] {
    opacity: .4;
  }
}
</style>
