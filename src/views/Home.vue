<template>
  <div class="home">
    <Sidebar />

    <CvContainer />
  </div>
</template>

<script>
// @ is an alias to /src
import Sidebar from "@/components/Sidebar.vue";
import CvContainer from "@/components/CvContainer.vue";

export default {
  name: "Home",
  components: { Sidebar, CvContainer },
};
</script>

<style lang="scss" scoped>
.home {
  display: flex;
}

.sidebar {
  width: 20%;
  max-width: 20%;
}

.cv-container {
  width: 80%;
}
</style>
