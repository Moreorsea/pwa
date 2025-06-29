<template>
  <div class="wrapper">
    <div class="container">
      <div class="icon">📶</div>
      <h1>Нет подключения к интернету</h1>
      <p>К сожалению, ты - лох, пидор, нет друзей и интернета</p>
      <p>Но вот что ты можешь попробовать:</p>
      <ul style="text-align: left; margin-bottom: 1.5rem">
        <li>Проверить подключение к Wi-Fi или мобильным данным</li>
        <li>Просто ждать - как только интернет появится, страница перезагрузится сама</li>
        <li>Пойти погулять, а-то снова лето проебешь</li>
      </ul>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
.container {
  width: 500px;
  padding: 2rem;
  background: white;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  position: relative;
  margin: 100px auto;
}
h1 {
  color: #d32f2f;
  margin-top: 0;
}
p {
  margin-bottom: 1.5rem;
  line-height: 1.6;
}
.icon {
  font-size: 4rem;
  margin-bottom: 1rem;
  color: #d32f2f;
  text-align: center;
}
button {
  background: #4285f4;
  color: white;
  border: none;
  padding: 0.8rem 1.5rem;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
  transition: background 0.3s;
}
button:hover {
  background: #3367d6;
}
</style>
