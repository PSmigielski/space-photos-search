<template>
    <div class="textWrapper">
        <h1>Space photos</h1>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Est laborum deleniti cum quia, doloremque unde id ipsam voluptatum inventore iste.</p>
    </div>
</template>
<script>
export default {
  name: 'Content',
};
</script>
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
  .textWrapper{
    width: 40%;
    height: 40%;
    color: white;
    font-family: inherit;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    text-shadow: 2px 2px #000000;
    text-align: center;
    margin-bottom: 30px;
  }
  h1{
    font-family: 'Poppins', sans-serif;
    font-weight: 400;
    font-size: 48px;
  }
  p{
    font-family: 'Poppins', sans-serif;
    font-weight: 300;
    font-size: 24px;
  }
  @media screen and (max-width:900px){
    .textWrapper{
      margin-bottom: 50px;
    }
    h1{
      font-size:36px;
    }
    p{
      font-size: 20px;
    }
  }
  @media screen and (max-width:630px) {
    .textWrapper{
      width: 60%;
    }
  }
    @media screen and (max-width:420px) {
    .textWrapper{
      width: 90%;
    }
  }

</style>
