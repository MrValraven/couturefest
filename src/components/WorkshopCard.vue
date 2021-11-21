<template>
  <div class="workshopCard">
    <div class="cardHeader">
      <h2>Alta costura 101</h2>
      <p>Intermédio</p>
    </div>
    <div class="instrutor">
      <img src="@/assets/modelo.jpg" alt="" />
      <p>Maria isaltina</p>
    </div>
    <p>
      Neste workshop irá aprender a ser a melhor costureira da sua vizinhança.
      Faça com que as suas vizinhas fiquem a roer de inveja
    </p>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.workshopCard {
  width: 400px;
  border: 2px solid steelblue;
  border-radius: 12px;
  padding: 25px 15px;
  margin-right: 50px;
  margin-top: 50px;
  flex: 0 0 25%;

  .cardHeader {
    display: flex;
    justify-content: space-between;

    h2 {
      font-size: 25px;
    }

    p {
      padding: 5px;
      background-color: orangered;
      color: white;
      border-radius: 6px;
    }
  }

  .instrutor {
    display: flex;
    margin-bottom: 10px;
    img {
      height: 25px;
      width: 25px;
      border-radius: 50%;
    }

    p {
      font-size: 16px;
    }
  }
}
</style>
