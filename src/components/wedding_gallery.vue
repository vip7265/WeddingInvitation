<template>
  <div class="container">
    <div class="title"><p>Gallery</p></div>
    <div class="wedding-container" v-if="clicked">
      <div class="wedding-bg-shadow">
        <div class="wedding-bg" @click="touch = !touch">
          <transition name="fade">
            <div class="image-index" v-if="touch">
              {{ current + 1 }}/20
            </div>
          </transition>
          <div class="close-btn" @click="handleCloseBtn" >
            <i class="fas fa-times fa-2x"></i>
          </div>
          <div class="wedding-bg-img">
            <img :src="require(`@/assets/images/img${current+1}.jpg`)" loading="lazy"/>
          </div>
          <div class="imgController">
            <button class="controller-left" @click="handleBtn1" v-if="touch">
              <i class="fas fa-chevron-left fa-3x"></i>
            </button>
            <button class="controller-right" @click="handleBtn2" v-if="touch">
              <i class="fas fa-chevron-right fa-3x"></i>
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- 썸네일  -->
    <div class="thubmnail-bg" v-if="!clicked">
      <img :src="require('@/assets/images/thumbnail.png')"/>
      <!-- 클릭박스 -->
      <div class="img-1" @click="clicked=true;current=0"></div>
      <div class="img-2" @click="clicked=true;current=1"></div>
      <div class="img-3" @click="clicked=true;current=2"></div>
      <div class="img-4" @click="clicked=true;current=3"></div>
      <!-- 1열 -->
      <div class="img-5" @click="clicked=true;current=4"></div>
      <div class="img-6" @click="clicked=true;current=5"></div>
      <div class="img-7" @click="clicked=true;current=6"></div>
      <div class="img-8" @click="clicked=true;current=7"></div>
      <!-- 2열 -->
      <div class="img-9" @click="clicked=true;current=8"></div>
      <div class="img-10" @click="clicked=true;current=9"></div>
      <div class="img-11" @click="clicked=true;current=10"></div>
      <div class="img-12" @click="clicked=true;current=11"></div>
      <!-- 3열 -->
      <div class="img-13" @click="clicked=true;current=12"></div>
      <div class="img-14" @click="clicked=true;current=13"></div>
      <div class="img-15" @click="clicked=true;current=14"></div>
      <div class="img-16" @click="clicked=true;current=15"></div>
      <!-- 4열 -->
      <div class="img-17" @click="clicked=true;current=16"></div>
      <div class="img-18" @click="clicked=true;current=17"></div>
      <div class="img-19" @click="clicked=true;current=18"></div>
      <div class="img-20" @click="clicked=true;current=19"></div>
      <!-- 5열 -->
    </div>

    <div v-if="clicked" class="empty-space"></div>
    
    <div class="wedding-map">
      <p style="font-size:2rem;">오시는 길</p>
      <!--<img src="@/assets/images/map.jpg" />-->
      <div class="main-info">
        <p style="font-weight:bold;">서울대학교 교수회관</p>
        <p>08826 서울시 관악구 관악로1 서울대학교 교수회관(65동)</p>
        <div id="map" style="width:100%;height:500px;"></div>
      </div>

      <div class="main-info-2">
        <p style="font-weight:bold;">지하철 이용시</p>
        <p>2호선 낙성대역 하차 시: 4번출구(낙성대방향) 나와서 낙성주유소 뒤편 2번 마을버스 탑승<br>
          ※ 마을버스 정거장 “노천강당 정류장 또는 공동기기원 정류장”
          <br><br>
          2호선 서울대입구역 하차 시 : 3번출구(서울대방향) 나와서 5511버스 탑승<br>
          ※ 버스 정거장 “공동기기원”
        </p>
        <br>
        <p style="font-weight:bold;">기타 이용시</p>
        <p>서울대역, 낙성대역에서 택시로 5~10분 소요. <br/>
            서울대 후문을 지나 기숙사 삼거리에서 왼쪽으로 올라 오십시오. <br/>
            서울대 정문 들어와 좌회전 – 직진 - 기숙사삼거리에서 오른쪽 직진. <br/>
            <p style="color: brown;">※ 낙성대 근처의 (호암교수회관)이 아닙니다.</p>
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      clicked: false,
      touch: true,
      current: 0,
    };
  },
  mounted() { 
    if (window.kakao && window.kakao.maps) {
      this.initMap()
    } else {
      const script = document.createElement('script')
      script.onload = () => window.kakao.maps.load(this.initMap);
      script.src = 'http://dapi.kakao.com/v2/maps/sdk.js?autoload=false&appkey=cce889e7ce1b029ca09261197dfe7c84'
      document.head.appendChild(script)
    }
  },

  methods: {
    handleBtn1() {
      this.touch = false;
      if (this.current == 0) {
        this.current = 19;
      } else {
        this.current -= 1;
      }
    },
    handleBtn2() {
      this.touch = false;
      if (this.current == 19) {
        this.current = 0;
      } else this.current += 1;
    },
    handleCloseBtn(){
      this.clicked = !this.clicked;
    },
    initMap () {
      const container = document.querySelector('#map')
      const options = {
        center: new window.kakao.maps.LatLng(37.45784171496702, 126.95389416739197),
        level: 3
      }
      const map = new window.kakao.maps.Map(container, options)
      const markerPosition = new window.kakao.maps.LatLng(37.45784171496702, 126.95389416739197);

      const marker = new window.kakao.maps.Marker({
        position: markerPosition
      });
      marker.setMap(map)
    }
  },
};
</script>

<style scoped>
.container {
  max-width: 768px;
  margin:0 auto;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.title p {
  font-size: 1.8rem;
  margin: 0 auto;
  padding-left: 1.5rem;
  padding-bottom: 3rem;
  letter-spacing: 1.5rem;
}
.image-index {
  color: rgba(255, 255, 255, 0.918);
  margin: 0;
  padding: 0;
  position: absolute;
  top: 2rem;
  left: 2rem;
  font-size: 1.6rem;
}
.wedding-container{
  display:flex;
  justify-content: center;
  margin:0 auto;
}
.wedding-bg {
  position: relative;
  margin: 0 auto;
  align-items: center;
  display: flex;
}
.wedding-bg-shadow {
  background: black;
  position: absolute;
  height: 120%;
  display: flex;
}
.wedding-bg-img{
  margin:0 auto;
  max-width:500px;
}
.wedding-bg-img img {
  width:100%;
  animation: fadein 400ms ease-in-out forwards;
}
.close-btn {
  position: absolute;
  top: 2rem;
  right: 2rem;
  color: white;
  opacity: 0.7;
}
.imgController {
  display: flex;
  align-items: center;
  justify-content: center;
}
.imgController button {
  background: none;
  border: none;
  position: absolute;
  color: white;
  opacity: 0.7;
  animation: fadein 400ms ease-in-out forwards;
}
.controller-left {
  left: 0;
}
.controller-right {
  right: 0;
}
.img-1,.img-2,.img-3,.img-4 {
  top: 0.8rem;
  position: absolute;
  width: 22%;
  height:16%;
  display: flex;
  justify-content: center;
}
.img-5,.img-6,.img-7,.img-8 {
  top: 21%;
  position: absolute;
  width: 22%;
  height:17%;
  display: flex;
  justify-content: center;
}
.img-9,.img-10,.img-11,.img-12 {
  top: 42%;
  position: absolute;
  width: 22%;
  height:16%;
  display: flex;
  justify-content: center;
}
.img-13,.img-14,.img-15,.img-16 {
  top: 62%;
  position: absolute;
  width: 22%;
  height:16%;
  display: flex;
  justify-content: center;
}
.img-17,.img-18,.img-19,.img-20 {
  top: 82%;
  position: absolute;
  width: 22%;
  height:16%;
  display: flex;
  justify-content: center;
  
}
.img-1,.img-5,.img-9,.img-13,.img-17{
  left: 1%;
}
.img-2,.img-6,.img-10,.img-14,.img-18 {
  left: 26%;
}
.img-3,.img-7,.img-11,.img-15,.img-19 {
  left: 51%;
}
.img-4,.img-8,.img-12,.img-16,.img-20 {
  left: 77%;
}
.thubmnail-bg{
  position: relative;
  width:100%;
  margin:0 auto;
  display: flex;
  justify-content: center;
 background: rgb(243, 243, 243);
}
.thubmnail-bg img{
  width:100%;
  height:100%;
}
.wedding-map {
  margin-top: 10rem;
  padding:0 1rem;
  letter-spacing: 1.3rem;
  margin-bottom: 3rem;
  height: 120rem;
}
.empty-space {
  position: relative;
  height: 80rem;
  z-index: -1;
}
@keyframes fadein {
  0%{
    opacity: 0;
  }
  100%{
    transition: opacity 0.3s;
  }
}
@keyframes fadeout {
 from{
   opacity: 1;
 }
 to{
   opacity: 0;
 }
}
.map-font p {
  text-align: center;
  font-size: 1.7rem;
}
.main-info p {
  font-size: 2rem;
  letter-spacing: 0rem;
}
.main-info-2 p {
  text-align: left;
  letter-spacing: 0rem;
  font-size: 1.5rem;
}
.#map { 
  overflow: auto;
  width:400px;
  height:100%; 
}
</style>
