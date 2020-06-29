<template>
    <div class="circle1">
      <div class="circle2">
      </div>
    </div>
</template>

<script>
export default {
  name: 'Loader',
};
</script>

<style lang="scss" scoped>
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
  border-right: 5px solid white;
  border-bottom: 5px solid red;
  border-top: 5px solid white;
  border-left: 5px solid red;
  border-radius: 50%;
  box-sizing: border-box;
  animation: spin 0.5s 1s linear infinite;
}

</style>
