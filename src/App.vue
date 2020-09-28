<template>
  <div id="app">
    <h1>Tốn thời gian suy nghĩ hôm nay ăn gì.</h1>
    <h2>Thử món này xem:</h2>
    <a
      v-bind:href="dish_google_place_search_url"
      target="_blank"
      rel="noopener"
    >
      {{ dish_name }}
    </a>

    <p>Ăn vui vẻ nhá!</p>
  </div>
</template>

<script>
var arr = [
  "Bánh bèo",
  "Bánh căn",
  "Bánh canh",
  "Bánh khọt",
  "Bánh tráng thịt heo",
  "Bánh xèo",
  "Bê thui",
  "Bò kho",
  "Bún bò Huế",
  "Bún cá rô đồng",
  "Bún cá",
  "Bún chả cá",
  "Bún mắm",
  "Cao lầu",
  "Cháo lươn",
  "Cơm niêu",
  "Cơm tấm",
  "Gà nướng",
  "Hủ tiếu",
  "Mì Quảng",
  "Ốc",
  "Thịt dê",
];

console.log(arr.length);
var random_index = Math.floor(Math.random() * arr.length);
console.log(random_index);

export default {
  name: "App",
  data() {
    var selected_dish_name = arr[random_index];
    return {
      dish_name: selected_dish_name,
      dish_google_place_search_url:
        "https://www.google.com/maps/search/" +
        selected_dish_name.split(" ").join("+"),
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
