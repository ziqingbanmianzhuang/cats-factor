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
      <a href="https://www.axios-http.cn/docs/example">
        <img src="https://img.shields.io/badge/axios-1.6.2-black
" alt="">
      </a>
    </side>
    <main class="features-box">
      <div>
        <h2>Developer 1</h2>
        <p>My name is Zhang Li. Cats are one of my favorite animals. There are many stray cats in our school. They often
          comfort me when I am frustrated. This world cannot be without cats. This is our common home.</p>
      </div>
      <div>
        <h2>Developer 1</h2>
        <p>My name is Jin Yan. I also like cats very much. Every time I see their cute faces, I am encouraged that cats
          are our partners and we should protect them and love them.</p>
      </div>
    </main>
    <footer>
      <ul>
        <li>
          <h1>Email</h1>
          <p>17292371124@qq.com<br>
            3351858214@qq.com<br>
            1290924026@qq.com
          </p>
        </li>
        <li>
          <h1>Phone:</h1>
          <p>18608263452<br>
            14708271028<br>
            17381144397

          </p>
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
