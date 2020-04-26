<template>
  <div class="container">
    <p>HOST --- {{ host }}!</p>
    <!-- <p>Where am I running? {{ name }}!</p> -->
  </div>
</template>

<script>
import axios from "axios";
import os from "os";
export default {
  async asyncData() {
    const response = await axios({
      method: "get",
      url: "https://lustig-cloud-run.web.app/"
    });

    return {
      host: os.hostname()
    };
  }
};
</script>

<style scoped>
.container {
  font-size: 20px;
  text-align: center;
  padding-top: 100px;
}
</style>
