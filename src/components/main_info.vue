<template>
  <div class="container">
    <div class="main-picture">
      <img src="@/assets/images/head.jpg" />
    </div>
    <div class="main-info">
      <div class="main-info-title">
        <p>The Marriage Of</p>
        <p>/ 배인표 & 한지은 /</p>
      </div>
      <div class="main-info-location">
        <p>2022년 5월 1일 일요일 정오 12시 30분</p>
        <p>서울대학교 교수회관 예식장</p>
      </div>
      <div class="divide-line"></div>
      <div class="main-greeting">
        <div class="main-greeting-title">
          <p>5월 1일</p>
          <p>배대식 ∙ 도경숙의 <span>장남</span> 인표</p>
          <p>한규석 ∙ 박두례의 <span>장녀</span> 지은</p>
          <p>결혼합니다</p>
        </div>
        <div class="main-greeting-text">
          <p>함께 있을 때 가장 나다운 모습이 되고</p>
          <p>함께 있을 때 미래를 꿈꾸게 하는 사람을 만났습니다</p>
          <br/>
          <p>그 사람과 같은 방향을 바라보고</p>
          <p>인생이라는 여행을 함께 시작하려합니다</p>
          <p>사랑으로 함께 가는 길,</p>
          <p>행복한 가정으로 가꾸어 갈 수 있도록</p>
          <p>귀한 걸음하시어 축복해주시면</p>
          <p>큰 기쁨으로 간직하겠습니다</p>
        </div>
      </div>
    </div>
    <div class="divide-line"></div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.container{
  max-width:768px;
  margin:0 auto;
  width:100%;
}
.main-picture {
  display: flex;
  align-items: center;
  justify-content: center;
}
.main-picture img {
  width: 100%;
}
.main-info {
  width: 100%;
  height: 82rem;
}
.main-info-title p {
  justify-content: center;
  align-items: center;
  display: flex;
  font-size: 2rem;
  letter-spacing: 0.8rem;
}
.main-info-location p {
  font-size: 1.5rem;
  text-align: center;
  margin: 0;
}
.divide-line {
  margin: 3rem 3rem;
  border: 0.7px solid rgb(218, 218, 218);
}
.main-greeting {
  margin: 0 auto;
  padding: 0 2.3rem;
  text-align: center;
}
.main-greeting-title {
  padding-bottom: 4rem;
}
.main-greeting-title p {
  letter-spacing: 0.3rem;
  font-size: 1.5rem;
  margin: 0.4rem 0;
}
.main-greeting-title p span {
  font-size: 1.2rem;
}
.main-greeting-text p {
  font-size: 1.27rem;
  margin-top: 0.5rem;
  padding: 0.3rem 0;
}
.main-greeting-text {
  margin-bottom: 3rem;
}
.bottom-img {
  overflow: hidden;
}
.bottom-img img {
  width: 100%;
  transform: translate(0, -8%);
}
@media (min-width: 350px) {
  .main-info {
    height: 120rem;
  }
  .main-info-location p {
  font-size: 1.7rem;
}
  .main-greeting-title {
  padding-bottom: 4rem;
}
  .main-greeting-title p span {
    font-size: 1.4rem;
  }
  .main-greeting-title p {
    font-size: 1.7rem;
  }
  .main-greeting-text p {
    font-size: 1.4rem;
    margin-top: 0.5rem;
    padding: 0.3rem 0;
  }
  .main-greeting {
    margin: 0 auto;
  }
  .divide-line {
    margin: 3rem 2rem;
  }
  .bottom-img {
    height:100%;
  overflow: hidden;
}
.bottom-img img {
  transform: translate(0, -60%);
}
}
@media (min-width: 380px) {
  .main-info {
    height: 95rem;
  }
  .main-greeting {
    padding: 0 2.7rem;
  }
  .divide-line {
    margin: 3rem 2.5rem;
  }
    .main-greeting-text p {
    font-size: 1.5rem;
    margin-top: 0.5rem;
    padding: 0.3rem 0;
  }
}
@media (min-width: 420px) {
  .main-info {
    height: 95rem;
  }
  .main-info-title p {
    font-size:2.3rem;
}
.main-info-location p {
  font-size: 1.7rem;
}
  .main-greeting-title p span {
    font-size: 1.4rem;
  }
  .main-greeting-title p {
    font-size: 1.8rem;
  }
  .main-greeting-text p {
    font-size: 1.6rem;
    margin-top: 0.5rem;
    padding: 0.3rem 0;
  }
  .main-greeting {
    padding: 0 3rem;
  }
  .bottom-img {
    height: 100%; 
  }
  .bottom-img img {
  transform: translate(0, -8%);
}
  .divide-line {
    margin: 3rem 3rem;
  }
}
</style>
