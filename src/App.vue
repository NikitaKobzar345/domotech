/* eslint-disable */

<template>
  <form>
    <input class="searchField" placeholder="Поиск" />
  </form>
  <div class="buttons">
    <button class="greenButton">Загрузить</button>
    <button class="purpleButton">Загрузить</button>
    <button class="yellowButton">Загрузить</button>
  </div>

  <div class="cards">
    <h1>
      {{ products["image"] }}
    </h1>

    <h2>
      {{ products["shortText"] }}
    </h2>
    <h3>
      {{ products["datePublish"] }}
    </h3>
  </div>
</template>

<script>

export default {
  data() {
    return { products: [] };
  },

  created() {
    fetch("https://domotekhnika.ru/api/v1/news?page=10")
      .then((response) => response.json())
      .then((requestData) => (this.products = requestData.data.news[0]));
  },
};
</script>

<style>
/*  Кнопки   */

.buttons {
  display: flex;
  bottom: 0;
  position: absolute;
  margin-right: 668.5px;
  transform: translate(80%);
}

.greenButton {
  display: flex;
  width: 175;
  height: 56;

  border: 0;
  background-color: rgba(55, 139, 96, 1);
  color: white;
  border-radius: 36px;

  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 16px 32px;
  gap: 10px;

  position: relative;
  width: 175px;

  background-image: url("images/VectorPig.png");
  background-repeat: no-repeat;
  background-position: calc(100% - 13px);
}

.purpleButton {
  width: 175;
  height: 56;

  margin-left: 29px;
  border: 0;
  background-color: rgba(255, 0, 184, 1);
  color: white;
  border-radius: 36px;

  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 16px 32px;
  gap: 10px;

  position: relative;
  width: 175px;
  height: 56px;

  background-image: url("images/VectorFire.png");
  background-repeat: no-repeat;
  background-position: calc(100% - 13px);
}

.yellowButton {
  width: 175;
  height: 56;

  margin-left: 29px;
  border: 0;
  background-color: rgba(251, 150, 0, 1);
  color: white;
  border-radius: 36px;
  display: flex;

  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 16px 32px;
  gap: 10px;

  position: relative;
  width: 175px;
  height: 56px;

  background-image: url("images/VectorStroke.png");
  background-repeat: no-repeat;
  background-position: calc(100% - 13px);
}

/*  Форма   */

.searchField {
  display: flex;
  margin: auto;
  width: 1346px;
  height: 21px;
  top: 12px;
  left: 18px;
  font-family: "Roboto";
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 130%;

  color: #4d4d4d;

  flex: none;
  order: 0;
  flex-grow: 0;

  background: url("images/Subtract.png") right no-repeat;
  background-position: calc(100% - 19px);

  border-radius: 5px;
}
</style>
