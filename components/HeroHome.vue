<template lang="pug">
  .relative.flex.justify-center.min-h-screen.bg-gray-900.items-center
    #stars
    #stars2
    #stars3
    #title
    .max-w-4xl.mx-auto
      .text-white.text-center
        img.w-56.rounded-full.border-8.border-white.inline-block(src="../static/me.jpeg")
        p.text-7xl.font-hand.font-bold.mt-6 Arturo Guerrero
        p.text-xl.mt-3 Software Developer
        .mt-3
          a(href="google.com")
            font-awesome-icon.mx-2(:icon="['fab', 'linkedin']" size="2x")
          font-awesome-icon.mx-2(:icon="['fab', 'github']" size="2x")
          font-awesome-icon.mx-2(:icon="['fab', 'dev']" size="2x")
</template>
<script>
export default {
  name: 'HeroHome'
}
</script>
<style lang="sass">

.font-fira
  font-family: 'Source Code Pro', monospace

.font-hand
  font-family: 'Kaushan Script', cursive

@function multiple-box-shadow ($n)
  $value: '#{random(2000)}px #{random(2000)}px #FFF'
  @for $i from 2 through $n
    $value: '#{$value} , #{random(2000)}px #{random(2000)}px #FFF'

  @return unquote($value)

$shadows-small:  multiple-box-shadow(700)
$shadows-medium: multiple-box-shadow(200)
$shadows-big:    multiple-box-shadow(100)

html
  height: 100%
  background: radial-gradient(ellipse at bottom, #1B2735 0%, #090A0F 100%)
  overflow: hidden

#stars
  width: 1px
  height: 1px
  background: transparent
  box-shadow: $shadows-small
  animation: animStar 50s linear infinite

  &:after
    content: " "
    position: absolute
    top: 2000px
    width: 1px
    height: 1px
    background: transparent
    box-shadow: $shadows-small

#stars2
  width: 2px
  height: 2px
  background: transparent
  box-shadow: $shadows-medium
  animation: animStar 100s linear infinite

  &:after
    content: " "
    position: absolute
    top: 2000px
    width: 2px
    height: 2px
    background: transparent
    box-shadow: $shadows-medium

#stars3
  width: 3px
  height: 3px
  background: transparent
  box-shadow: $shadows-big
  animation:  animStar 150s linear infinite

  &:after
    content: " "
    position: absolute
    top: 2000px
    width: 3px
    height: 3px
    background: transparent
    box-shadow: $shadows-big

#title
  position: absolute
  top: 50%
  left: 0
  right: 0

  color: #FFF
  text-align: center
  font-family: 'lato',sans-serif
  font-weight: 300
  font-size: 50px
  letter-spacing: 10px

  margin-top: -60px
  padding-left: 10px

  span
    background: -webkit-linear-gradient(white, #38495a)
    -webkit-background-clip: text
    -webkit-text-fill-color: transparent

@keyframes animStar
  from
    transform: translateY(0px)
  to
    transform: translateY(-2000px)

</style>
