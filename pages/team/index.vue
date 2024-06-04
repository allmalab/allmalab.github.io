<template>
  <div>
    <div class="team-header">Meet our team</div>
    <div class="team-card-wrapper">
      <div class="team-card" v-for="(item, index) in teamMembers" :key="index">
        <img :src="item.img" :alt="item.name" class="team-card__photo" />
        <div class="team-card__name">{{ item.name }}</div>
        <div class="team-card__about">{{ item.about }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import team_member_1 from "~/assets/images/team-member-1.png";
import team_member_2 from "~/assets/images/team-member-2.jpeg";
import team_member_3 from "~/assets/images/team-member-3.jpg";

const teamMembers = [
  {
    img: team_member_1,
    name: "Jafar Isbarov",
    about:
      "Lead machine learning engineer at PRODATA LLC. MSc student at George Washington University.",
  },
  {
    img: team_member_2,
    name: "Kavsar Huseynova",
    about:
      "Machine learning engineer at PRODATA LLC. BSc Compter Engineering student at Baku Higher Oil School.",
  },
  {
    img: team_member_3,
    name: "Elvin Mammadov",
    about:
      "Junior data scientist at PRODATA LLC. BSc Process Automation Engineering student at Baku Higher Oil School.",
  },
];
</script>

<style lang="scss" scoped>
.team-header {
  font-size: 50px;
  color: #333333;
  margin-bottom: 3.75rem;
  font-family: "SpaceGrotesk", sans-serif;
  font-weight: 700;
}

.team-card-wrapper {
  display: flex;
  flex-direction: column;
  gap: 3.13rem;
}

.team-card__photo {
  border-radius: 15px;
  width: 19.38rem;
  height: 16.63rem;
  object-fit: cover;
  margin-bottom: 1.88rem;
}

.team-card__name {
  font-size: 24px;
  margin-bottom: 1.25em;
  font-weight: 700;
  color: #001122;
}

.team-card__about {
  max-width: 19.38rem;
  font-size: 20px;
  color: #888888;
  font-weight: 500;
}

@media (min-width: 1050px) {
  .team-card-wrapper {
    flex-direction: row;
    gap: 3.75rem;
  }
  .team-card__about {
    max-width: 21.86rem;
  }
  .team-card__photo {
    width: 29.38rem;
  }

  .team-header {
    font-family: "SpaceGrotesk", sans-serif;
  }
}
</style>
