<template>
  <transition name="spin">
    <div class="circle1">
      <transition name="spin2">
        <div class="circle2"></div>
      </transition>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'Loader',
};
</script>

<style lang="scss" scoped>
.spin-enter-active {
  animation: spin .5s linear infinite;
}
.spin-leave-active {
  animation: spin .5s linear infinite;
}
.spin2-enter-active {
  animation: spin .5s linear infinite;
}
.spin2-leave-active {
  animation: spin .5s linear infinite;
}
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
.circle1 {
  display: flex;
  justify-content: space-around;
  align-items: center;
  box-sizing: border-box;
  width: 50px;
  height: 50px;
  border: 5px solid red;
  border-bottom: 5px solid transparent;
  border-top: 5px solid red;
  border-left: 5px solid transparent;
  border-radius: 50%;
  margin:20px 0px 20px 0px;
  animation: spin 0.5s 1s linear infinite;
}
.circle2 {
  width: 30px;
  height: 30px;
  border: 5px solid red;
  border-right: 5px solid transparent;
  border-bottom: 5px solid red;
  border-top: 5px solid transparent;
  border-left: 5px solid red;
  border-radius: 50%;
  box-sizing: border-box;
  animation: spin 0.5s 1s linear infinite;
}

</style>
