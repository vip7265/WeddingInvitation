<template>
  <div class="footer">
    <ul>
      email: jhn5052@naver.com
      <a href="https://github.com/jhn5052">Github: minji</a>
    </ul>
    <ul>
      © 2022. All Rights Reserved.
    </ul>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  font-size:1.2rem;
}
a{
  color:black;
  text-decoration: black;
  list-style-type: style;
}
.footer {
  background: #ceb2e4;
  height: 5rem;
  display: flex;
  flex-direction: column;
  align-content: center;
  align-items: center;
  justify-content: center;
  color: black;
  font-weight: bold;
  padding-bottom: 1rem;
}
ul{
  opacity: 0.7;
}
</style>