<template>
  <div class="home">
    <div class="container">

      <div class="site-content">
      <h1>We are the World!</h1>
      <h2>
        If we can share love and ideas, the world could be a better place for all
      </h2>
    </div>

    <div class="log-in">
      <Login />
    </div>
    </div>
    
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Login from '@/components/Login.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
    Login
  }
}
</script>

<style scoped>
.home {
  padding-top: 72px;
  padding-bottom: 112px;
}
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  padding: 0 150px;
}
.site-content {
  text-align: left;
  width: 50%;
  color: black;
  padding-top: 50px;
}
.site-content h1 {
  color: #2c3e50;
  font-size: 50px;
  font-weight: normal;
  line-height: 32px;
}
.site-content h2 {
  font-size: 28px;
  font-weight: normal;
  line-height: 32px;
  width: 500px;
}
</style>