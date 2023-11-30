<template>
    <div class="home">
        <header>
            <img src="../assets/cats.jpg" alt="">
            <h1>cat factor</h1>
        </header>
        <nav>
            <router-link to="/" class="home-nav">home</router-link>
            <router-link to="/show" calss="show-nav">find</router-link>
            <router-link to="/about" calss="about-nav">about</router-link>
        </nav>
    </div>
</template>
  
<script>
// @ is an alias to /src


export default {
    name: 'navPage',
}
</script>

<style scoped>
.home {
    display: flex;
    justify-content: space-between;
}

.home header {
    display: flex;
    align-items: center;
    justify-content: space-evenly;
}

.home header img {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    margin-right: 30px;
}

.home nav {
    min-width: 200px;
    display: flex;
    justify-content: space-between;
    align-items: center;

}

.home nav a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;
}

.home nav a.router-link-exact-active {
    display: block;
    background-color: rgb(85, 90, 218);
    border-radius: 10px;
    width: 60px;
    height: 20px;
    color: #fff;
}
</style>
  