<template>
  <div class="home">
    <h2>build a light cats lifePlace</h2>
    <p>learn about the cutest creatures in the world - kittens</p>
    <a href="#show-pic">Let's start!!!!!</a>
    <section class="show-pic">
      <div class="box-1">
        <img src="../assets/home-4.jpg" alt="">
      </div>
      <div class="box-2">
        <img src="../assets/home-1.jpg" alt="">
      </div>
      <div class="box-3">
        <img src="../assets/home-5.jpg" alt="">
      </div>
      <div class="box-4">
        <img src="../assets/home-6.jpg" alt="">
      </div>
      <div class="box-5">
        <img src="../assets/home-2.jpg" alt="">
      </div>
      <div class="box-6">
      </div>
      <div class="box-7">
        <img src="../assets/home-3.jpg" alt="">
      </div>

    </section>
    <section class="main-info-box" id="show-pic">
      <div class="intro">
        <div class="text-box">
          <h3>a home for your company video</h3>
          <p> Our lovely little friend-Cat:Cats are cute animals, usually with soft fur and flexible bodies. They have
            large, bright eyes and pointed ears. Cats are agile and lively and like to play and chase toys. They are
            usually very independent, but also enjoy interacting with humans. Cats are one of the most common pets that
            bring people happiness and companionship..</p>
        </div>
        <div class="img-box">
          <img src="../assets/home-7.jpg" alt="">
        </div>
      </div>
      <ul>
        <li>
          <h4>Sleepy:</h4>
          <p> Cats typically need 14 to 15 hours of sleep per day, although their actual sleeping time is only
            about
            4
            to 5 hours.</p>
        </li>
        <li>
          <h4>Willful</h4>
          : Cats do not listen to their owner's commands like dogs do, but view them as equal partners.
          <p></p>
        </li>
        <li>
          <h4> Cleanliness</h4>
          : Cats will regularly groom their own fur and often lick their bodies to remove dirt and grime.
          <p></p>
        </li>
      </ul>
    </section>
    <section class="main-side-box">
      <h3>video message features</h3>
      <ul>
        <li>
          <h4> 1.flexible body:</h4>
          <p>Cats have soft bodies and agile movements, allowing them to quickly catch prey and climb</p>
        </li>
        <li>
          <h4>2.Sharp senses:</h4>
          <p>tomorawo is creatues in the wousan kietens builds a lisfhti sdk</p>
        </li>
        <li>
          <h4>3.Independent and autonomous:</h4>
          <p>
            Cats usually display an independent personality and like to move alone, but they
            can
            also form close relationships with humans.</p>
        </li>
        <li>
          <h4> 4.Strong adaptability: </h4>
          <p> Cats can adapt to various environments, ranging from household pets to urban stray cats,
            and can survive and reproduce.</p>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'HomeView',
}

</script>

<style scoped>
.home::-webkit-scrollbar {
  display: none;
  width: 0px;
  background-color: transparent;
}

.home {
  width: 100vw;
  height: 100vh;
  overflow-x: hidden;
  scroll-behavior: smooth;
}

.home>h2,
.home>p {
  color: rgb(64, 53, 97);
}

.home>a {
  display: block;
  width: 150px;
  text-align: center;
  line-height: 30px;
  border-radius: 20px;
  background-color: rgba(85, 91, 220);
  border: none;
  color: #fff;
  height: 30px;
  margin: 0 auto;
  text-decoration: none;
}

.show-pic {
  position: relative;
  height: 300px;
}

.show-pic .box-1 {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: purple;
  position: absolute;
  left: -10px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.show-pic .box-1 img {
  width: 45px;
  height: 45px;
  border-radius: 50%;

}

.show-pic .box-2 {
  width: 150px;
  height: 200px;
  border-radius: 10px;
  background-color: purple;
  position: absolute;
  left: -20px;
  top: 70px;
}

.show-pic .box-2 img {
  width: 150px;
  height: 200px;
  border-radius: 10px;
  border: 2px solid rgba(128, 0, 128);
}

.show-pic .box-3 {
  width: 90px;
  height: 200px;
  border-radius: 10px;
  background-color: purple;
  position: absolute;
  left: 170px;
  top: 70px;
}

.show-pic .box-3 img {
  width: 90px;
  height: 200px;
  border-radius: 10px;
  border: 2px solid rgba(128, 0, 128);


}

.show-pic .box-4 {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: purple;
  position: absolute;
  left: 310px;
  top: 70px;
}

.show-pic .box-4 img {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  border: 2px solid rgba(128, 0, 128);


}

.show-pic .box-5 {
  width: 300px;
  height: 150px;
  border-radius: 10px;
  background-color: purple;
  position: absolute;
  left: 400px;
  top: 30px;
}

.show-pic .box-5 img {
  width: 300px;
  height: 150px;
  border-radius: 10px;
  border: 2px solid rgba(128, 0, 128);


}

.show-pic .box-6 {
  width: 70px;
  height: 50px;
  border-radius: 30px;
  background-color: purple;
  position: absolute;
  right: -20px;
  top: 30px;
}

.show-pic .box-7 {
  width: 70px;
  height: 170px;
  border-radius: 10px;
  background-color: purple;
  position: absolute;
  right: -20px;
  top: 100px;
}

.show-pic .box-7 img {
  width: 70px;
  height: 170px;
  border-radius: 10px;
  border: 2px solid rgba(128, 0, 128);


}


.main-info-box {
  width: 90%;
  background-color: rgba(42, 28, 79);
  border-radius: 30px;
  color: #fff;
  margin: 0 auto;
}

.main-info-box .intro {
  display: flex;
  justify-content: space-around;
}

.main-info-box .intro .text-box h3 {
  font-size: 25px;
  padding: 0 30px;
  text-align: left;
}

.main-info-box .intro .text-box p {
  font-size: 14px;
  padding: 0 30px;
  text-align: left;
}

.main-info-box .intro .img-box img {
  width: 350px;
  height: 300px;
  margin: 30px;
  border-radius: 30px;
}

.main-info-box ul {
  display: flex;
  justify-content: space-around;
  list-style: none;
  text-align: left;
}

.main-side-box ul {
  list-style: none;
  display: flex;
}

.main-side-box ul li h4 {
  width: 10px;
  color: rgba(63, 53, 96);
  position: relative;
  left: 25px;
}

.main-side-box ul li h4:before {
  content: "&";
  display: block;
  position: absolute;
  left: -25px;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  color: #ccc;
  background-color: rgba(50, 37, 89);
}

.main-side-box ul li {
  text-align: left;
  padding: 10px;
}
</style>
