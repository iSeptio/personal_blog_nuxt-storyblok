<template>
  <div v-editable="blok" class="feature util__flex-eq">

    <div id="phone">
      <img src="~/assets/PHONE.svg" /><img src="~/assets/RESPONSIVE.svg" />
</div>
    <h1>{{ blok.name }} </h1>
    <div class="feature__description">
      {{ blok.description }}
    </div>

  </div>
</template>

<script>
export default {
  props: ['blok']
}
</script>

<style lang="scss">
.feature {
  text-align: center;
  padding: 30px 10px 100px;
}

.feature__icon {
  max-width: 80px;
}


#phone {
  position:relative;
  width: 80px;
  text-align:left;
  padding: 5px;
}

#phone :first-child {
  position: absolute;
  z-index: 2;
}

#phone :nth-child(2) {
  position: absolute;
  margin-top: 32%;
  margin-left: 20%;
  width: 60%;
  z-index: 3;
  opacity: 0;
}

#phone:hover > :nth-child(2) {
  animation-duration: 1.2s;
  animation-name: animateLogo;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
@keyframes animateLogo {
  from {
    transform: translateX(0) translateY(0);
  }
  to {
    opacity: 100;
    transform: translateX(-23px) translateY(23px);
  }
}


</style>
