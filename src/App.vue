<template>
  <div id="app">
    <div id="intro">Không biết hôm nay ăn gì?!</div>
    <div class="regular">Thử món này xem:</div>
    <div id="suggestion_area">
      <a
        id="google_search_link"
        v-bind:href="dish_google_place_search_url"
        target="_blank"
        rel="noopener"
      >
        {{ dish_name }}
      </a>
      <br />
      <a
        id="google_place_search_url"
        v-bind:href="dish_google_place_search_url"
        target="_blank"
        rel="noopener"
      >
        Tìm quán trên bản đồ
      </a>
    </div>
    <div class="regular">Ăn uống vui vẻ nhá!</div>
    <a href="https://github.com/nqtrg/angibaygio" target="_blank">
      <img
        id="github_profile_icon"
        alt="Github profile"
        src="./assets/github_icon/github_profile_icon.png"
      />
    </a>
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

var random_index = Math.floor(Math.random() * arr.length);

export default {
  name: "App",
  data() {
    var selected_dish_name = arr[random_index];
    var dish_google_place_search_url =
      "https://www.google.com/maps/search/" +
      selected_dish_name.split(" ").join("+");
    return {
      dish_name: selected_dish_name,
      dish_google_place_search_url: dish_google_place_search_url,
    };
  },
};
</script>
