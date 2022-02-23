<template>
    <div>
        <nav id="nav" :class="{ active: isActive }">
        <!-- <router-link @click="toggleNav" to="/">Home</router-link> -->
        <!-- <router-link @click="toggleNav" to="/about">About</router-link> -->

        <router-link @click="toggleNav" :to="{ name: 'Blogs' }">Blogs</router-link>
        <router-link @click="toggleNav" :to="{ name: 'AddBlog' }"
        >Create Blog</router-link
        >
        <router-link @click="logout" class="logout" :to="{ name: 'Home' }"
        >Log out</router-link
        >
        <!-- <router-link @click="toggleNav" :to="{ name: 'Login' }">Login</router-link> -->
        <!-- <router-link @click="toggleNav" :to="{ name: 'Signup' }"
        >Register</router-link
        > -->
        </nav>
        <button id="nav-btn" @click="toggleNav">
            <i className="fas fa-bars"></i>
        </button>
    </div>
  
</template>
<script>
export default {
  data() {
    return {
      isActive: false,
    };
  },
  methods: {
    toggleNav() {
      this.isActive = !this.isActive;
    },
    logout() {
      localStorage.clear();
      this.toggleNav;
    },
  },
};
</script>
<style>
#nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: #f5f5f5;
  box-shadow: 8px 8px 15px #e4e4e4, -8px -8px 15px #ffffff;
}
#nav-btn {
  position: fixed;
  top: 20px;
  right: 20px;
  background: #f5f5f5;
  box-shadow: 8px 8px 15px #e4e4e4, -8px -8px 15px #ffffff;
  padding: 20px;
  border-radius: 50%;
  border: none;
  outline: none;
  display: none;
}
#nav {
  padding: 30px;
}
#nav .router-link-exact-active:not(.logout) {
      color: #42b983;
    }
#nav a {
    font-weight: bold;
    color: #2c3e50;
    padding: 20px;
    text-decoration: none;
}
@media screen and (max-width: 500px) {
  #nav {
    height: 100%;
    left: -100vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    transition: left 0.1s linear;
  }
  #nav.active {
    left: 0;
  }
  #nav-btn {
    display: block;
  }
}
</style>
