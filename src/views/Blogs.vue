<template>
<Navbar />
  <div v-if="blogs">
    <h2>Blogs</h2>
    <div class="blogs-container" v-if="blogs">
      <router-link
        v-for="blog of blogs"
        :key="blog._id"
        :to="{ name: 'BlogDetails', params: { id: blog._id } }"
      >
        <img :src="blog.image" :alt="blog.title" />
        {{ blog.author_name }}
      </router-link>
    </div>
  </div>
  <div v-else>Loading blogs...</div>
 
</template>
<script>

// import Navbar from '../components/Navbar.vue'
import Navbar from '@/components/Navbar.vue'
export default {
  components: { Navbar },
  data() {
    return {
      blogs: null,
    };
  },
  
  mounted() {
    if (localStorage.getItem("jwt")) {
      fetch("http://localhost:3000/posts", {
        method: "GET",
        headers: {
          "Content-type": "application/json; charset=UTF-8",
          Authorization: `Bearer ${localStorage.getItem("jwt")}`,
        },
      })
        .then((response) => response.json())
        .then((json) => {
          this.blogs = json;
          console.log(json)
          this.blogs.forEach(async (blog) => {
            await fetch(
              "http://localhost:3000/users/" + blog.user_id,
              {
                method: "GET",
                headers: {
                  "Content-type": "application/json; charset=UTF-8",
                  Authorization: `Bearer ${localStorage.getItem("jwt")}`,
                },
              }
            )
              .then((response) => response.json())
              .then((json) => {
                blog.author_name = json.name;
              });
          });
        })
        .catch((err) => {
          alert("User not logged in");
        });
    } else {
      alert("User not logged in");
      this.$router.push({ name: "Home" });
    }
  },
};
</script>
<style>
.blogs-container {
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  margin-inline: auto;
  padding: 30px;
  gap: 2%;
  justify-content: stretch;
  align-items: stretch;
  flex-direction: column;
}
img {
  max-width: 50vw;
}
</style>
