<template>
  <div class="blog-article-wrapper">
    <div class="blog-article__title">Ml Consulting</div>
    <div class="blog-article__body">
      <div class="body__header">
        <span>ML Consulting:</span> From strategy development to implementation
        and optimization, our consulting services cover the entire ML lifecycle,
        helping you leverage data to drive business success.
      </div>
      <div class="body__header">
        <span>Mobile Applications:</span> Apps designed for smartphones and
        tablets to provide various functionalities, such as communication,
        entertainment, productivity, or utility.
      </div>
      <div class="body__content">
        <ul>
          <li>
            <span>Web-Based Platforms:</span> Online platforms accessible
            through web browsers, offering services like e-commerce, social
            networking, content management, or online collaboration.
          </li>
          <li>
            <span>Cloud Computing Services:</span> Infrastructure, platforms, or
            software delivered over the internet, allowing users to store,
            manage, and process data remotely, without the need for on-premises
            hardware or infrastructure.
          </li>
          <li>
            <span>Big Data and Analytics Tools:</span> Technologies for
            collecting, analyzing, and interpreting large volumes of data to
            derive insights and support decision-making processes.
          </li>
          <li>
            <span>Internet of Things (IoT) Solutions:</span> Connected devices
            and sensors that gather data from the physical world and communicate
            it over the internet for monitoring, control, or automation
            purposes.
          </li>
          <li>
            <span
              >Artificial Intelligence (AI) and Machine Learning (ML)
              Applications:</span
            >
            Algorithms and systems that mimic human intelligence to perform
            tasks such as natural language processing, image recognition,
            predictive analytics, or autonomous decision-making.
          </li>
          <li>
            <span>Blockchain Technologies:</span>
            Distributed ledgers that provide secure, transparent, and
            tamper-proof records of transactions or data exchanges, commonly
            used in financial services, supply chain management, or digital
            identity verification.
          </li>
          <li>
            <span>Cybersecurity Solutions:</span>
            Tools and protocols designed to protect digital systems, networks,
            and data from unauthorized access, cyberattacks, or data breaches.
          </li>
          <li>
            <span
              >Virtual Reality (VR) and Augmented Reality (AR)
              Experiences:</span
            >
            Immersive technologies that blend digital content with the
            real-world environment to create interactive simulations, training
            programs, or entertainment experiences.
          </li>
          <li>
            <span>Robotic Process Automation (RPA):</span>
            Software robots that automate repetitive tasks, workflows, or
            business processes, enabling organizations to increase efficiency
            and reduce operational costs.
          </li>
        </ul>
      </div>
    </div>
    <div class="blog-article__footer">
      <div class="footer__author">Jafar Isbarov</div>
      <div class="footer__username">@jafar</div>
    </div>
  </div>
</template>

<script setup>
// const { id } = useRoute().params;

// const blogPosts = [
//   {
//     id: 1,
//     title: "ML Consulting",
//     content: "",
//     author: "Jafar Isbarov",
//     username: "@jafar",
//   },
// ];
</script>

<style lang="scss" scoped>
.blog-article-wrapper {
  color: #666666;
  padding: 0 20px;
}

.blog-article__title {
  font-size: 50px;
  color: #333333;
  font-family: "SpaceGrotesk", sans-serif;
  font-weight: 700;
  margin-bottom: 20px;
}

.body__header {
  span {
    font-weight: bold;
    color: #333333;
  }
}

.blog-article__body {
  display: flex;
  flex-direction: column;
  gap: 30px;
  line-height: 1.8rem;
}

.body__content {
  span {
    font-weight: bold;
    color: #333333;
  }
  ul {
    margin: 0;
  }
}

.blog-article__footer {
  margin-top: 10px;
  text-align: end;
  .footer__author {
    font-size: 20px;
    color: #001122;
    font-weight: 600;
  }
  .footer_username {
    font-size: 14px;
    color: #666666;
  }
}

@media (min-width: 1020px) {
  .blog-article-wrapper {
    max-width: 1000px;
  }
}
</style>
