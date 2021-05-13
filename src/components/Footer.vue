<template>
  <footer>
    <div class="all-foot">
      <div class="copyright">
        <p>{{ name }} &copy; {{ copyright }}</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      name: "Sanket Upreti",
      copyright: "2021",
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

footer {
  position: relative;
  background: midnightblue;
  color: mintcream;
  font-size: 24px;
  font-family: "Times New Roman", Times, serif;
  padding: 10px 5px;
}

.copyright {
  max-width: 90%;
  text-align: center;
}
</style>
