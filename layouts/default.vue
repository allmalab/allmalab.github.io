<template>
  <div class="wrapper">
    <header>
      <Navbar />
    </header>
    <div class="body">
      <slot />
    </div>
    <div class="footer">
      <div>© 2024 aLLMA Lab. All rights reserved.</div>
      <img
        src="/assets/images/prodata_logo.png"
        alt="prodata-logo"
        class="prodata-logo"
      />
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.wrapper {
  background-color: #f5f3ef;
  height: 100%;
}
.body {
  padding: 2.5rem 0;
  display: flex;
  justify-content: center;
  min-height: 100vh;
}

header {
  border-bottom: 1px solid #e1e0dc;
}

.footer {
  color: #8f8f8f;
  height: 85px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid #e1e0dc;
  padding: 0 40px 0 50px;
  .prodata-logo {
    width: 116px;
    height: 19px;
  }
}

@media (min-width: 950px) {
  .wrapper {
    height: 100%;
  }

  .body {
    height: 100%;
  }

  header {
    border-bottom: 1px solid #e1e0dc;
  }
}
</style>
