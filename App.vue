<template lang="pug">
div
  .banner
    TopBar
    .container
      .row: .text-container
        h1.banner__title To Make Your Life Easier Take a Card
        p.banner__text There are many variations of passages of Lorem Ipsum available, but the majority have suffered There are many variations of passages of Lorem Ipsum randomised words which don't look even slightly believable.
        button.banner_btn.btn.btn--round.btn--normal(type="button") Apply Now
      .row
        .cards-container
          img.card-image-one(src="~assets/card-image.png")
          img.card-image-two(src="~assets/card-image.png")
          img.card-image-three(src="~assets/card-image.png")
    img.cards-deco-ico(src="~assets/cards-deco-ico.png")
    img.cards-deco-shapes(src="~assets/cards-deco-shapes.png")
  section.process: .container
    .section-title
      div Easy Process
      h2 To Get Credit Card
    .row
      ProcessCards
  section.service: .container
    .row: .section-title
      div useful service avaible
      h2 Service of Credit Card
    .row
      Carousel
  section.factoids
    .container: .row
      .factoid
        img.factoid__ico(src="~assets/fact-ico-1.png")
        .factoid__fact 725M
        .factoid__text Happy User
      .factoid
        img.factoid__ico(src="~assets/fact-ico-2.png")
        .factoid__fact 700M
        .factoid__text User Apprication
      .factoid
        img.factoid__ico(src="~assets/fact-ico-3.png")
        .factoid__fact 10M+
        .factoid__text Payment Service
      .factoid
        img.factoid__ico(src="~assets/fact-ico-4.png")
        .factoid__fact 600M
        .factoid__text User Feedback
  section.feedback: .container
    .row: h3 Your Message
    .row: form.feedback-form(action="")
      .feedback-form__left
        input.form-control(type="text" name="name" placeholder="Your Name")
        input.form-control(type="email" name="email" placeholder="Email Address")
        input.form-control(type="text" name="subject" placeholder="Subject")
      .feedback-form__right
        textarea.form-control(placeholder="Message")
        input.btn.form-btn(type="submit" value="Submit")
  footer.site-footer
    .footer-copyright Copyright @ Digital Marketing. AllRight Reseverd

</template>

<script>
import TopBar from '~components/TopBar.vue'
import ProcessCards from '~components/ProcessCards.vue'
import Carousel from '~components/Carousel.vue'

export default {
  components: {
    TopBar,
    ProcessCards,
    Carousel
  },
  created: function () {
    console.log('Привет, Артсофте!')
  }
}
</script>

<style lang="scss">
@import url(normalize.css);
@import url("~fonts/fonts.scss");

html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}
body {
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.5;
  color: #222;
  text-align: left;
}
h3 {
  font-family: "Poppins", sans-serif;
  font-weight: 600;
  font-size: 30px;
  color: #333;
  margin: 0;
}

.container {
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
  @media screen and (min-width: 576px) {
    max-width: 540px;
  }
  @media screen and (min-width: 768px) {
    max-width: 720px;
  }
  @media screen and (min-width: 992px) {
    max-width: 960px;
  }
  @media screen and (min-width: 1200px) {
    max-width: 1170px;
  }
}

.row {
  display: flex;
  flex-wrap: wrap;
  margin-left: -15px;
  margin-right: -15px;
}

.btn {
  display: inline-block;
  font-weight: 400;
  text-align: center;
  vertical-align: middle;
  user-select: none;
  font-size: 1rem;
  font-family: "Poppins", sans-serif;
  font-weight: 600;
  line-height: 1;
  color: #0b4bec;
  text-transform: initial;
  text-decoration: none;
  background: white;
  transition: box-shadow .15s ease-in-out;
  border: 1px solid transparent;

  &--round {
    border-radius: 22px;
  }
  &--roundSmall {
    border-radius: 12px;
  }
  &--small {
    padding: 8px 12px;
    font-size: 14px;
  }
  &--normal {
    padding: 15px 50px;
    font-size: 14px;
    text-transform: uppercase;
  }

  &:hover {
    box-shadow: 0px 3px 3px rgba(30, 28, 28, .75);
  }
}
[type="button"]:not(:disabled),
button:not(:disabled) {
  cursor: pointer;
}

.banner {
  background: linear-gradient(to top, rgba(#071d68, 1), rgba(#0b4bec, 1));
  position: relative;
  overflow: hidden;
}

.text-container {
  text-align: center;
  color: white;
  width: 100%;
  flex: 0 0 calc(100% / 12 * 10);
  max-width: calc(100% / 12 * 10);
  margin: 60px auto 60px;

  @media (min-width: 992px) {
    margin: 120px auto 0;
  }
  @media (min-width: 1200px) {
    margin: 170px auto 0;
  }
}
.banner__title {
  font-family: "Poppins", sans-serif;
  font-weight: 600;
  line-height: 1.5;
  font-size: 32px;
  @media (min-width: 992px) {
    font-size: 40px;
    line-height: 0.65;
  }
}
.banner__text {
  font-size: 14px;
  font-family: "Nunito", sans-serif;
  line-height: 2;
}
.banner_btn {
  margin-top: 40px;
}

.cards-container {
  display: none;
  position: relative;
  width: 100%;
  height: 509px;
  justify-content: center;

  @media (min-width: 992px) {
    display: flex;
    margin-top: 90px;
  }
}
.card-image-one,
.card-image-two,
.card-image-three {
  position: absolute;
  display: block;
}
.card-image-one {
  z-index: 4;
  max-width: 100%;
  height: auto;
}
.card-image-two,
.card-image-three {
  z-index: 3;
  opacity: .4;
  width: 415px;
  height: 370px;
  top: 60px;
}
.card-image-two {
  left: 0;
}
.card-image-three {
  right: 0;
}

.cards-deco-ico,
.cards-deco-shapes {
  display: none;

  @media (min-width: 576px) {
    display: block;
    position: absolute;
    z-index: 2;
  }
}
.cards-deco-ico {
  @media (min-width: 576px) {
    top: 45%;
    left: -5%;
  }
  @media (min-width: 992px) {
    top: 20%;
    left: -5%;
  }
  @media (min-width: 1200px) {
    top: 30%;
    left: 15%;
  }
}
.cards-deco-shapes {
  @media (min-width: 576px) {
    top: 25%;
    right: -25%;
  }
  @media (min-width: 992px) {
    top: 5%;
    right: -20%;
  }
  @media (min-width: 1200px) {
    top: 25%;
    right: 0;
  }
}

.section-title {
  text-transform: uppercase;
  color: #808080;
  font-family: "Poppins", sans-serif;
  font-weight: normal;
  font-size: 20px;
  line-height: 1.75;

  @media (min-width: 992px) {
    font-size: 24px;
  }

  h2 {
    color: #333;
    font-weight: bold;
    font-size: 24px;
    line-height: 1.4;
    margin: 0;

    @media (min-width: 992px) {
      font-size: 30px;
    }
  }
}
.process {
  background-color: #f3f2f2;
  padding: 75px 0 100px;

  .section-title {
    text-align: center;
  }

  @media (min-width: 1200px) {
    padding: 150px 0 200px;
  }
}
.service {
  padding: 80px 15px;

  @media (min-width: 1200px) {
    padding: 160px 0;
  }
}
.factoids {
  background: #0b4bec url("~assets/factoids-bg.jpg") no-repeat;
  padding: 75px 0 40px;

  .row {
    justify-content: space-between;
    align-items: baseline;

    @media (min-width: 768px) {
      flex-wrap: nowrap;
    }
  }

  @media (min-width: 992px) {
    padding: 175px 0;
    max-height: 550px;
  }
}
.factoid {
  color: #fff;
  font-family: "Poppins", sans-serif;
  text-align: center;
  width: 100%;
  flex: 0 0 calc(100% / 12 * 6);
  max-width: calc(100% / 12 * 6);
  padding: 0 15px;
  margin-bottom: 55px;

  @media (min-width: 768px) {
    flex: initial;
    max-width: initial;
    margin-bottom: 0;
  }
}
.factoid__fact {
  font-weight: 600;
  font-size: 26px;
  line-height: 1.3;
  margin-top: 25px;

  @media (min-width: 992px) {
    font-size: 52px;
    margin-top: 50px;
  }
}
.factoid__text {
  font-size: 16px;
  line-height: 1.666;

  @media (min-width: 992px) {
    font-size: 24px;
  }
}

.feedback {
  padding: 65px 15px 75px;

  @media (min-width: 992px) {
    padding: 130px 0 150px;
  }
}
.feedback-form {
  width: 100%;
  display: flex;
  flex-flow: column;

  margin-top: 25px;

  @media (min-width: 992px) {
    margin-top: 50px;
  }

  .form-control {
    margin-bottom: 15px;

    @media (min-width: 992px) {
      margin-bottom: 30px;
    }
  }
  textarea.form-control {
    height: 130px;
    resize: none;
  }

  @media (min-width: 992px) {
    flex-flow: row;
  }
}
.feedback-form__left,
.feedback-form__right {
  width: 100%;

  @media (min-width: 992px) {
    width: 50%;
  }
}
.feedback-form__right {

  @media (min-width: 992px) {
    margin-left: 35px;
  }
}
.feedback-form__left {

  @media (min-width: 992px) {
    margin-right: 35px;
  }
}
.form-control {
  display: block;
  width: 100%;
  padding: 17px 20px;
  font-size: 14px;
  font-weight: 400;
  line-height: 1;
  color: #333;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  transition: border-color .15s ease-in-out, box-shadow .15s ease-in-out;

  &::placeholder {
    color: #808080;
    font-family: "Raleway", sans-serif;
    font-size: 14px;
  }
}
.form-btn {
  background-color: #0b4bec;
  width: 100%;
  color: #fff;
  font-family: "Raleway", sans-serif;
  font-size: 14px;
  font-weight: normal;
  height: 50px;
  cursor: pointer;
}

.site-footer {
  background: #0b4bec url("~assets/footer-bg.jpg") no-repeat;
  padding: 40px 0 70px;
}
.footer-copyright {
  color: #fff;
  font-family: "Poppins", sans-serif;
  font-weight: normal;
  font-size: 14px;
  text-align: center;
}
</style>
