<template>
  <div>
    <div class="blog-header">Blogs</div>
    <div class="blogs-card-wrapper">
      <div class="blog-card" v-for="(item, index) in blogs" :key="index">
        <h2>{{ item.title }}</h2>
        <div class="blog-card__author">{{ item.author }}</div>
        <p>{{ item.content }}</p>
        <div class="blog-card__footer">
          <NuxtLink :to="`/blogs/${item.id}`">
            <div>Read more</div>
            <span>-></span>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useRoute } from "vue-router";
import { ref, onMounted } from "vue";

const route = useRoute();
const blogPost = ref({});

const blogs = [
  {
    id: "ml-consulting",
    title: "ML Consulting",
    author: "@jafar",
    content:
      "ML Consulting: From strategy development to implementation and optimization, our consulting services cover the entire ML lifecycle, helping you leverage data to drive business success.",
  },
  {
    id: "ml-consulting",
    title: "ML Consulting",
    author: "@jafar",
    content:
      "ML Consulting: From strategy development to implementation and optimization, our consulting services cover the entire ML lifecycle, helping you leverage data to drive business success.",
  },
  {
    id: "ml-consulting",
    title: "ML Consulting",
    author: "@jafar",
    content:
      "ML Consulting: From strategy development to implementation and optimization, our consulting services cover the entire ML lifecycle, helping you leverage data to drive business success.",
  },
  {
    id: "ml-consulting",
    title: "ML Consulting",
    author: "@jafar",
    content:
      "ML Consulting: From strategy development to implementation and optimization, our consulting services cover the entire ML lifecycle, helping you leverage data to drive business success.",
  },
  {
    id: "ml-consulting",
    title: "ML Consulting",
    author: "@jafar",
    content:
      "ML Consulting: From strategy development to implementation and optimization, our consulting services cover the entire ML lifecycle, helping you leverage data to drive business success.",
  },
  {
    id: "ml-consulting",
    title: "ML Consulting",
    author: "@jafar",
    content:
      "ML Consulting: From strategy development to implementation and optimization, our consulting services cover the entire ML lifecycle, helping you leverage data to drive business success.",
  },
];

onMounted(() => {
  const blogId = route.params.id;
  blogPost.value = blogs.find((blog) => blog.id === parseInt(blogId)) || {};
});
</script>

<style lang="scss" scoped>
.blog-header {
  font-size: 50px;
  color: #333333;
  margin-bottom: 3.75rem;
  font-family: "SpaceGrotesk", sans-serif;
  font-weight: 700;
}

.blogs-card-wrapper {
  display: grid;
  grid-template-columns: repeat(1, 20rem);
  gap: 1.25rem;
}

.blog-card {
  // border: 1px solid #bfbfbf;
  padding: 2.5rem 1.75rem 2.31rem;
  border-radius: 15px;
  background: #fafafa;
  box-shadow: 3px 5px 6px #00000033;
}

h2 {
  color: #001122;
  margin: 0;
}

p {
  color: #666666;
  margin: 0.625rem 0 2.81rem;
}

.blog-card__footer {
  padding: 0 0.625rem;
  font-weight: 600;
  cursor: pointer;
  a {
    text-decoration: none;
    color: #000;
    display: flex;
    justify-content: space-between;
    align-items: center;
    span {
      color: #6666ff;
      font-size: 1.5rem;
    }
  }
}

.blog-card__author {
  font-size: 14px;
  color: #666666;
}

@media (min-width: 680px) {
  .blogs-card-wrapper {
    grid-template-columns: repeat(2, 20rem);
  }
}

@media (min-width: 1020px) {
  .blogs-card-wrapper {
    grid-template-columns: repeat(3, 20rem);
  }
}
</style>
