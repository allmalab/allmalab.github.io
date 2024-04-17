<template>
  <div>
    <div class="contribute-header">Contribute</div>
    <div class="contribute-card-wrapper">
      <div
        :class="[
          'contribute-card',
          { 'full-screen': index === cards.length - 1 },
        ]"
        v-for="(item, index) in cards"
        :key="index"
      >
        <div class="contribute-card__header">{{ item.header }}</div>
        <div class="contribute-card__content">{{ item.content }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
const cards = [
  {
    header: "Use our resources!",
    content:
      "We are releasing open-source resources for people interested in developing NLP systems for Azerbaijani. Your first contribution to our cause would be using these resources (maybe provide feedback). If you have used our datasets or models to build something, we would love to hear your story.",
  },
  {
    header: "Open source",
    content:
      "We also encourege our users to contribute to the process. This can include pull requests on GitHub, but also simpler (although as important!) things like feature requests and bug reports.",
  },
  {
    header: "Mentorship program",
    content:
      "We are unable to offer a paid internship at this time, but we offer mentorship to ambitious individuals who want to get started in open-source NLP projects. You can send us an email at jafar.isbarov@prodata.az.",
  },
  {
    header: "Full-time jobs",
    content:
      "aLLMA Lab is sponsored by PRODATA LLC. Company dedicates substantial engineering time and hardware resources to the lab. If you want to work at aLLMA Lab and get paid for it, your best bet is to apply for a job at NLP team of PRODATA. aLLMA Lab also collaborates with other organisations, although those relationships are more prone to change.",
  },
];
</script>

<style lang="scss" scoped>
.contribute-header {
  font-size: 50px;
  color: #333333;
  margin-bottom: 3.75rem;
  font-family: "SpaceGrotesk", sans-serif;
  font-weight: 700;
}

.contribute-card-wrapper {
  display: grid;
  grid-template-columns: repeat(1, 20rem);
  gap: 1.25rem;
}

.contribute-card {
  padding: 1.88rem;
  border-radius: 15px;
  // background-color: #fff;
  background: #fafafa;
  box-shadow: 3px 5px 6px rgba(0, 0, 0, 0.2);
}

.contribute-card__header {
  font-size: 20px;
  color: #001122;
  margin-bottom: 1.88rem;
  font-weight: 700;
}

.contribute-card__content {
  font-size: 16px;
  color: #666666;
  font-weight: 500;
}

@media (min-width: 680px) {
  .contribute-card-wrapper {
    grid-template-columns: repeat(2, 20rem);
  }
}

@media (min-width: 1020px) {
  .contribute-card-wrapper {
    grid-template-columns: repeat(3, 20rem);
  }
  .full-screen {
    grid-column: 1 / -1;
    width: 58.75rem;
    margin-top: 2.5rem;
    // height: 6.25rem;
  }
}
</style>
