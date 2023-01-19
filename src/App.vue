<template>
  <button type="button" @click="flag = !flag">Toggle</button>
  <Transition name="fade" mode="out-in" appear>
    <h1 v-if="flag">Hello World!</h1>
    <h1 v-else>Another Hello</h1>
  </Transition>

  <transition name="zoom" appear>
    <h2 v-show="flag">Hello</h2>
  </transition>
</template>

<script>
  export default{
    name: "App",
    data() {
      return{
        flag: true,
      }
    },

  }
</script>

<style>
.fade-enter-from{
  opacity: 0;
}
.fade-enter-active{
  transition: all 1s linear;
}
.fade-leave-to{
  transition: all 1s linear;
  opacity: 0;
}

.zoom-enter-active{
  animation: zoom-in 1s linear;
  transition: all 1s linear;
  opacity: 1;
}
.zoom-leave-active{
  animation: zoom-out 1s linear;
  transition: all 1s linear;
  opacity: 0;
}

@keyframes zoom-in{
  from{
    transform: scale(0, 0);
  }
  to{
    transform: scale(1, 1);
  }
}

@keyframes zoom-out{
  from{
    transform: scale(1, 1);
  }
  to{
    transform: scale(0, 0);
  }
}
</style>