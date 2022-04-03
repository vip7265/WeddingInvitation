<template>
  <div class="container">
    <div class="title">
      <p>/2022.05.01/</p>
      <div class="desc">일요일 정오 12시 30분</div>
    </div>
    <div class="divide-line"></div>

    <div class="day-row">
      <div v-for="day in days" :key="day" :class="day.style">
        {{ day.name }}
      </div>
    </div>
    <div class="date-column">
      <div class="week1">
        <div
          v-for="week in week1"
          :key="week"
          :class="week.style"
          :id="week.id"
        >
          {{ week.date }}
          <div v-if="week.date == 1">
            <div id="Dday"></div>
          </div>
          <div v-if="week.date == 5">
            <div id="bar">어린이날</div>
          </div>
        </div>
      </div>
      <!-- 1주 -->
      <div class="week2">
        <div v-for="week in week2" :key="week" :class="week.style">
          {{ week.date }}
          <div v-if="week.date == 8">
            <div id="bar">석가탄신일</div>
          </div>
        </div>
      </div>
      <div class="week3">
        <div v-for="week in week3" :key="week" :class="week.style">
          {{ week.date }}
        </div>
      </div>
      <div class="week4">
        <div v-for="week in week4" :key="week" :class="week.style">
          {{ week.date }}
        </div>
      </div>
      <div class="week5">
        <div v-for="week in week5" :key="week" :class="week.style">
          {{ week.date }}
        </div>
      </div>
    </div>
    <div class="divide-line"></div>
    <div class="counting">인표<span>♥</span>지은의 결혼식이 {{ getDate }}</div>
    <div class="divide-line"></div>
  </div>
</template>

<script>
export default {
  computed: {
    getDate() {
      let count = new Date().getTime();
      let dday = new Date("may 01, 2022 0:00:00").getTime();
      let gap = dday - count;
      if (gap < 0) {
        return (
          Math.abs(Math.ceil(gap / (1000 * 60 * 60 * 24))) + "일 지났습니다."
        );
      }
      return Math.ceil(gap / (1000 * 60 * 60 * 24)) + "일 남았습니다.";
    },
  },
  data() {
    return {
      days: [
        { name: "Sun", style: "sun" },
        { name: "Mon", style: null },
        { name: "Tue", style: null },
        { name: "Wed", style: null },
        { name: "Thu", style: null },
        { name: "Fri", style: null },
        { name: "Sat", style: null },
      ],
      week1: [
        { date: 1, style: "num1", id: "num1" },
        { date: 2, style: null, id: null },
        { date: 3, style: null, id: null },
        { date: 4, style: null, id: null },
        { date: 5, style: "box holiday", id: "어린이날" },
        { date: 6, style: null },
        { date: 7, style: null },
      ],
      week2: [
        { date: 8, style: "box holiday", id: "석가탄신일" },
        { date: 9, style: null },
        { date: 10, style: null },
        { date: 11, style: null },
        { date: 12, style: null },
        { date: 13, style: null },
        { date: 14, style: null },
      ],
      week3: [
        { date: 15, style: "sun" },
        { date: 16, style: null },
        { date: 17, style: null },
        { date: 18, style: null },
        { date: 19, style: null },
        { date: 20, style: null },
        { date: 21, style: null },
      ],
      week4: [
        { date: 22, style: "sun" },
        { date: 23, style: null },
        { date: 24, style: null },
        { date: 25, style: null },
        { date: 26, style: null },
        { date: 27, style: null },
        { date: 28, style: null },
      ],
      week5: [
        { date: 29, style: "sun" },
        { date: 30, style: null },
        { date: 31, style: null },
        { date: null, style: null },
        { date: null, style: null },
        { date: null, style: null },
        { date: null, style: null },
      ],
    };
  },
};
</script>

<style scoped>
.container {
  max-width: 768px;
  width: 96%;
  margin: 3rem auto 12rem auto;
}
.divide-line {
  margin: 3rem 3rem;
  border: 0.7px solid rgb(218, 218, 218);
}
.title p {
  font-size: 1.7rem;
  margin: 0 auto;
  padding-left: 1rem;
  padding-bottom: 1rem;
  letter-spacing: 0.8rem;
  text-align: center;
}
.desc {
  width: 100%;
  font-size: 1.7rem;
  text-align: center;
  margin-bottom: 2rem;
}
.day-row {
  display: flex;
  justify-content: space-evenly;
  font-size: 1.4rem;
}
.date-column {
  display: flex;
  flex-direction: column;
  font-size: 1.4rem;
}
#bar {
  position: absolute;
  background: #d1b6e6;
  width: 5rem;
  color: white;
  font-size: 1.1rem;
}
.week1 {
  margin-right: 1rem;
}
.week1,
.week2,
.week3,
.week4,
.week5 {
  display: flex;
  justify-content: space-evenly;
  padding-top: 8%;
}
.week5 {
  margin-right: 8rem;
}
.box {
  text-align: center;
}
.num1 {
  color: white;
}
#Dday {
  z-index: -1;
  position: absolute;
  width: 3rem;
  height: 3rem;
  border-radius: 30px;
  transform: translate(-0.7rem, -2.5rem);
  background: #a588bb;
  text-align: center;
}
.holiday {
  opacity: 0.5;
}
.sun {
  color: rgba(255, 103, 57, 0.76);
  font-weight: bold;
}
.counting {
  text-align: center;
  font-size: 1.5rem;
}
.counting span {
  color: #c3a0df;
}
@media (max-width: 320px) {
  #bar {
    position: absolute;
    background: #d1b6e6;
    color: white;
    font-size: 1rem;
  }
}
</style>
