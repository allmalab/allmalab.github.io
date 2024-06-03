<template>
  <div>
    <div class="home-header">
      <div class="home-header__title">
        Open-source software, data, and language models.
      </div>
      <div class="home-header__about">
        We are a small team of engineers mostly located in Baku, Azerbaijan. Our
        goal is to provide open-source NLP resources for Azerbaijani.
      </div>
    </div>
    <div class="image-container">
      <a href="https://huggingface.co/allmalab" target="_blank">
        <img src="assets/images/hf.png" class="clickable-image" style="width:300px;height:auto;"/>
      </a>
      <a href="https://github.com/allmalab" target="_blank">
        <img src="assets/images/github.png" class="clickable-image" style="width:300px;height:auto;"/>
      </a>
    </div>
    <div class="home-blogs-wrapper">
      <div class="home-blog-card" v-for="(item, index) in blogs" :key="index">
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
import illustration from "/assets/images/illustration.svg";
import illustration2 from "/assets/images/illustration2.svg";
import prodata_logo from "~/assets/images/prodata_logo.png";
import banm_logo from "~/assets/images/banm_logo.png";

const blogs = [
];

const teamMembers = [
  {
    img: illustration,
    name: "Jafar Isbarov",
    role: "ML Engineer at PRODATA",
  }
];

const collaborations = [
  { img: prodata_logo, name: "prodata_logo" },
  { img: banm_logo, name: "banm_logo" },
];
</script>

<style lang="scss" scoped>
.home-header {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.home-header__title {
  width: 20.25rem;
  margin: 9.19rem 0 1.88rem;
  font-family: "SpaceGrotesk";
  font-weight: 700;
  font-size: 59px;
  text-align: center;
}

.home-header__about {
  width: 18.36rem;
  margin-bottom: 11.69rem;
  font-size: 20px;
  font-weight: 200;
  text-align: center;
}

.home-blogs-wrapper {
  display: grid;
  grid-template-columns: repeat(1, 20rem);
  gap: 1.25rem;
  justify-content: center;
  margin-bottom: 8.5rem;
}

.home-blog-card {
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
  min-height: 133px;
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

.home-team-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .home-team__header {
    font-family: "SpaceGrotesk", sans-serif;
    font-size: 30px;
    font-weight: 700;
    margin-bottom: 4rem;
  }
}

.home-team-members {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2.5rem;
  margin-bottom: 9.813rem;
  .home-team-card {
    display: flex;
    flex-direction: column;
    align-self: center;
    justify-content: center;
    padding: 1.125rem 3.313rem;
  }
  .team-card__name {
    text-align: center;
    font-size: 18px;
    color: #000000;
  }
  .team-card__role {
    text-align: center;
    font-size: 14px;
    color: #8f8f8f;
  }
}

.home-collaborations {
  .home-collaborations_title {
    font-family: "SpaceGrotesk", sans-serif;
    font-size: 30px;
    font-weight: 700;
    text-align: center;
    margin-bottom: 3.75rem;
  }
}

.home-collaborations__logos {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 112px;
  margin-bottom: 6.25rem;
  .prodata_logo {
    width: 171px;
    height: 27px;
  }

  .banm_logo {
    width: 169px;
    height: 83px;
  }
}

.image-container {
  display: flex;
  justify-content: space-between;
}

.clickable-image {
  width: 48%;
  cursor: pointer;
}

@media (min-width: 680px) {
  .home-blogs-wrapper {
    grid-template-columns: repeat(2, 20rem);
  }
  .home-header__title {
    width: 37.25rem;
  }

  .home-header__about {
    width: 36.36rem;
  }
}

@media (min-width: 800px) {
  .home-header__title,
  .home-header__about {
    width: 50rem;
  }

  .home-collaborations__logos,
  .home-team-members {
    flex-direction: row;
  }
}

@media (min-width: 1020px) {
  .home-blogs-wrapper {
    grid-template-columns: repeat(3, 20rem);
  }
}
</style>
