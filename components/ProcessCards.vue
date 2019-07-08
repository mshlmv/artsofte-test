<template lang="pug">
.process-cards-container
  .process-card
    img.process-card__ico(src="~assets/process-icon-1.png")
    .process-card__title Online Application
    .process-card__text Information in the database is published in two formats. It is available in PDF comparison according to type of credit card.
  .process-card.process-card--hit
    img.process-card__ico(src="~assets/process-icon-2.png")
    .process-card__title Get Approval
    .process-card__text Information in the database is published in two formats. It is available in PDF comparison according to type of credit card.
  .process-card
    img.process-card__ico(src="~assets/process-icon-3.png")
    .process-card__title Get Your Card
    .process-card__text Information in the database is published in two formats. It is available in PDF comparison according to type of credit card.
</template>

<script>
export default {
}
</script>

<style lang="scss">
.process-cards-container {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  margin-top: 45px;
  padding: 0 15px;

  @media (min-width: 1200px) {
    flex-wrap: nowrap;
    margin-top: 90px;
  }
}
.process-card {
  width: 100%;
  text-align: center;
  border: 1px solid #dbdada;
  background-color: #fff;
  padding: 50px 40px;
  transition: transform .5s ease-in-out;

  &:not(:last-child) {
    margin-bottom: 30px;
  }

  &:hover {
    transform: scale(1.1) translateY(-20px);
  }

  @media (min-width: 992px) {
    flex: 0 0 calc(100% / 12 * 4);
    max-width: calc(100% / 12 * 4);

    &:not(:last-child) {
      margin-bottom: 0;
    }
  }
  @media (min-width: 1200px) {
    flex-shrink: 1;
  }
}
.process-card--hit {

  border: none;
  background: linear-gradient(to top, rgba(#071d68, 1), rgba(#0b4bec, 1));
  padding: 60px 40px;

  @media (min-width: 992px) {
    padding: 90px 40px;
  }
  @media (min-width: 1200px) {
    margin: 0 30px;
  }
}
.process-card__ico {
  display: block;
  margin: 0 auto;
}
.process-card__title {
  margin-top: 30px;
  color: #000;
  text-transform: uppercase;
  font-size: 20px;
  font-family: "Poppins", sans-serif;
  font-weight: 600;

  .process-card--hit & {
    color: #fff;
  }
}
.process-card__text {
  color: #808080;
  font-family: "Raleway", sans-serif;
  font-size: 14px;
  margin-top: 30px;

  .process-card--hit & {
    color: #fff;
  }
}
</style>
