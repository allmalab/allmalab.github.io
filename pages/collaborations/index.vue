<template>
  <div>
    <div class="collaborations-header">Collaborations</div>
    <div class="collaborations-card-wrapper">
      <div
        class="collaborations-card"
        v-for="(item, index) in companies"
        :key="index"
      >
        <img
          :src="item.img"
          :alt="item.name"
          :class="`collaborations-card__${item.className}`"
        />
        <div class="collaborations-card__name">{{ item.name }}</div>
        <div class="collaborations-card__about">{{ item.about }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import prodata_logo from "~/assets/images/prodata_logo.png";
import ufaz_logo from "~/assets/images/ufaz_logo.png";
import banm_logo from "~/assets/images/banm_logo.png";

const companies = [
  {
    img: prodata_logo,
    className: "prodata_logo",
    name: "PRODATA LLC",
    about:
      "aLLMA Lab is sponsored by PRODATA LLC. Company dedicates substantial engineering time and hardware resources to the lab. aLLMA Lab is established and maintained by the NLP team at PRODATA.",
  },
  {
    img: ufaz_logo,
    className: "ufaz_logo",
    name: "French-Azerbaijani University (UFAZ)",
    about:
      "As part of PRODATA's collaboration with UFAZ, we routinely hire interns who work at our open-source projects.",
  },
  {
    img: banm_logo,
    className: "banm_logo",
    name: "BHOS AI",
    about:
      "We collaborate tightly with Baku Higher Oil School's AI lab. Our datasets contain data collected and cleaned by them.",
  },
];
</script>

<style lang="scss" scoped>
.collaborations-header {
  font-size: 50px;
  color: #333333;
  margin-bottom: 1.88rem;
  font-family: "SpaceGrotesk", sans-serif;
  font-weight: 700;
}

.collaborations-card-wrapper {
  display: grid;
  grid-template-columns: repeat(1, 18.31rem);
  gap: 3.75rem;
}

.collaborations-card {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.collaborations-card__prodata_logo {
  // border: 1px solid #878787;
  border-radius: 15px;
  width: 10.69rem;
  height: 1.69rem;
  padding: 8.31rem 3.81rem;
  background: #fafafa;
  box-shadow: 3px 5px 6px rgba(0, 0, 0, 0.2);
}

.collaborations-card__ufaz_logo {
  // border: 1px solid #878787;
  border-radius: 15px;
  width: 7.5rem;
  height: 3.78rem;
  padding: 7.31rem 5.43rem;
  background: #fafafa;
  box-shadow: 3px 5px 6px rgba(0, 0, 0, 0.2);
}

.collaborations-card__banm_logo {
  // border: 1px solid #878787;
  border-radius: 15px;
  width: 10.56rem;
  height: 5.16rem;
  padding: 6.62rem 3.93rem;
  background: #fafafa;
  box-shadow: 3px 5px 6px rgba(0, 0, 0, 0.2);
}

.collaborations-card__name {
  font-size: 24px;
  margin: 1.88rem 0 0.63rem;
  color: #333333;
  text-align: center;
  font-weight: 700;
}

.collaborations-card__about {
  font-size: 20px;
  color: #888888;
  text-align: center;
  font-weight: 500;
}

@media (min-width: 680px) {
  .collaborations-card-wrapper {
    grid-template-columns: repeat(2, 20rem);
  }
}

@media (min-width: 1020px) {
  .collaborations-card-wrapper {
    grid-template-columns: repeat(3, 20rem);
  }
}
</style>
