<template>
  <nav class="navbar">
    <h4>Azabenathi</h4>
    <p><router-link to="/home">Login</router-link></p>
  </nav>
  <div class="container">
    <h2>Welcome</h2>
    <p>Hello, my name is Azabenathi Pupuma. I am a Software Developer, from Cape Town, South Africa. On this blog I will be writing about basic fundamentals of web development to frontend development including basic backend development.</p>

    <p>Posts will be generic as I am still working on the project. If you would like to post, feel free to do so. Looking forward to collaborating with great minds</p>
  
  
    <div class="links">
      <div class="link"><a href="https://github.com/Mnangwe/" class="github" target="_blank">Github</a></div>
      <div class="link"><a href="https://azabenathipupuma.netlify.app/" class="portfolio" target="_blank">Portfolio</a></div>
    </div>
  </div>

</template>

<script>
export default {

}
</script>

<style>
:root{
  --skin: gray;
}
nav.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: #f5f5f5;
  box-shadow: 8px 8px 15px #e4e4e4, -8px -8px 15px #ffffff;
  display: flex;
  justify-content: space-around;
  /* height: 100px !important; */
}
.navbar p {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.navbar a {
  font-size: 20px;
  font-weight: bold;
  color: #2c3e50;
  padding: 20px;
  text-decoration: underline;
}

nav.navbar h4 {
  font-size: 25px;
  color: #2c3e50 !important;
  font-family: "Rubik", sans-serif;
  font-weight: 700;
  text-decoration: none;
  display: inline-block;
  position: relative;
  padding: 0 10px;
  line-height: 50px;
  /* margin-top: 5px; */
}

nav.navbar h4::before {
  content: "";
  height: 20px;
  width: 20px;
  position: absolute;
  top: 0;
  left: 0;
}

.container {
  padding-top: 80px;
  padding: 10px;
  margin: 100px auto;
  max-width: 900px;
}
.container h2 {
  font-size: 40px;
}
.container p {
  text-align: justify;
  padding-top: 1.5px;
  font-size: 18px;
  letter-spacing: .5px;
  line-height: 26px;
  color: #504e70;
  color: var(--text);
}

.navbar h4::before{
  border-left: 4px solid var(--skin);
  border-top: 4px solid var(--skin)
}

::before, ::after {
    box-sizing: border-box;
}

  nav.navbar h4::after {
  content: "";
  height: 20px;
  width: 20px;
  position: absolute;
  
  bottom: 0;
  right: 0;
}

.navbar h4::after {
  border-bottom: 4px solid var(--skin);
  border-right: 4px solid var(--skin);
}
.links {
  display: flex;
  justify-content: center;
}
.link {
  padding: 20px;
  background-color: #42b983;
  margin: 4px;
  border-radius: 50px;
}
.link a {
  text-decoration: none;
  color: #e4e4e4;
  font-weight: bold;
}
</style>