<template>
  <section class="home">
    <div class="home-container">
      <div class="photo" v-for="({media_path, title}, index) of photos" :key="index">
        <div class="photo-img">
            <img :src="media_path" :alt="title" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      photos: [],
    };
  },
  methods: {
    fetchPhotos() {
      fetch("https://rdevjs-apianimes.herokuapp.com/posts")
        .then((r) => r.json())
        .then((r) => (this.photos = r));
    },
    
  },
  created() {
    this.fetchPhotos();
    
  },
};
</script>

<style scoped>
.home {
  flex: 5;
  height: 100vh;
  padding: 32px;
}

.home-container {
    display: flex;
    justify-content: center;

    gap: 20px;
    flex-wrap: wrap;
}

.photo-img img{
    width: 300px;
    height: 300px;

    object-fit: cover;
}
</style>