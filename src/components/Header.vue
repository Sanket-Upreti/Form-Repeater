<template>
  <header>
    <div class="all">
      <div class="logo"></div>
      <div class="pageDescription">
        <p>{{ description }}</p>
      </div>
      <div class="home">
        <p>{{ Home }}</p>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      description: "Adding Multiple Forms",
      Home: "Home",
    };
  },
};
</script>
<style scoped>
* {
  margin: 0 0;
  padding: 0 0;
  box-sizing: border-box;
}

header {
  height: auto;
  max-width: 1400px;
  background: midnightblue;
  color: mintcream;
  font-size: 24px;
  font-family: "Times New Roman", Times, serif;
  padding: 10px 5px;
}

.all {
  display: flex;
}

.logo {
  background: url(/assets/logo.png) no-repeat;
}

.pageDescription {
  min-width: 90%;
  text-align: center;
}

.home p {
  display: flex;
  justify-content: flex-end;
  cursor: pointer;
}
</style>
