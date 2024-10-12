<template>
  <div class="container">
    <SearchBar @onSearchCity="onSearchCity"/>
    <WeatherInfo :weatherData ="props.weatherData" />
  </div>
</template>
<script setup>
import SearchBar from "./SearchBar.vue";
import WeatherInfo from "./WeatherInfo.vue";

const emits = defineEmits(['onSearchCity']);

//날씨 상태변수
const props = defineProps({
    weatherData: Object,
})
console.log(props.weatherData);

// 검색어 이벤트 함수
const onSearchCity = (city) => {
    console.log("city: ", city)
    emits('onSearchCity', city)
}

</script>
<style lang="scss" scoped>
    .container {
    padding: 20px;
    }
</style>