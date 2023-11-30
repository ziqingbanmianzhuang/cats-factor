<template>
  <div class="about">
    <h1>What tools we use</h1>
    <side class="tools-box">
      <a href="https://vuejs.org/">
        <img src="https://img.shields.io/badge/%40vue%2Fcli-5.0.5-green" alt="">
      </a>
      <a href="https://pnpm.io/"><img src="" alt=""><img src="https://img.shields.io/badge/pnpm-8.7.1-yellow
" alt=""></a>
      <a href="https://nodejs.org/en"><img src="https://img.shields.io/badge/node-18.17.1-skyblue
" alt=""></a>
      <a href="https://v3.router.vuejs.org/zh/installation.html"><img src="https://img.shields.io/badge/vueRouter-%5E4.0.3-pink
" alt=""></a>
      <a href="">axios</a>
    </side>
    <main class="features-box">
      <div>
        <h2>Developer 1</h2>
        <p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
      </div>
      <div>
        <h2>Developer 1</h2>
        <p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
      </div>
    </main>
    <footer>
      <ul>
        <li>
          <h1>Email</h1>
          <p>17292371124@qq.com</p>
        </li>
        <li>
          <h1>Phone:</h1>
          <p>18608263452</p>
        </li>
        <li>
          <h1>Address:</h1>
          <p>成都市双流区成都信息工程大学</p>
        </li>
      </ul>
    </footer>
  </div>
</template>
<style scoped>
.tools-box a {
  display: block;
}

.tools-box {
  display: flex;
  justify-content: space-around;
  margin-bottom: 80px;
}

.features-box {
  display: flex;
  justify-content: space-around;
  color: #5e4f94;

}

.features-box div:nth-child(1) {
  border-radius: 30px;
  width: 40vw;
  background-color: #eef0ff;
  display: flex;
  flex-direction: column;
  align-items: center;


}

.features-box div:nth-child(1) p,
.features-box div:nth-child(2) p {
  width: 80%;
  word-wrap: break-word;
}

.features-box div:nth-child(2) {
  border-radius: 30px;
  width: 40vw;
  background-color: #eef0ff;
  display: flex;
  flex-direction: column;
  align-items: center;
}

footer {
  background-color: #eef0ff;
  width: 100vw;
  color: #b6b2d4;
  height: 200px;
  margin-top: 100px;


}

footer ul {
  display: flex;
  list-style: none;
  justify-content: space-around;
  transform: translateY(60px);
}

footer ul li h1 {
  font-size: 20px;
}
</style>
