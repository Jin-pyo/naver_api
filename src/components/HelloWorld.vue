<template>
  <div class="hello">

    <naver-maps :width="600" :height="400" :mapOptions="mapOptions">
      <naver-marker :lat="36.3770426" :lng=" 127.3930804" @click="onMarkerClicked" @load="onMarkerLoaded"></naver-marker>
    </naver-maps>
   
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      mapOptions: {
        lat: 36.3770426,
        lng: 127.3930804,
        zoom: 17,
        zoomControl: true,
        zoomControlOptions: {position: 'TOP_RIGHT'},
        mapTypeControl: true,
      }
    }
  },
   methods:{
    // naver-marker는 다음과 같은 체이닝이 가능합니다.
    onMarkerLoaded(vue){
      vue.marker.setDraggable(true).setCursor('').setClickable(true);
    },
    onMarkerClicked(event){
      console.log(event); // 네이버 event 객체
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
