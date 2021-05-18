<template>
  <div class="h-10 bg-gray-400 shadow">
    <Dashbord />
    <Body />
  </div>
</template>

<script>
import Dashbord from "./components/Dashbord";
import Body from "./components/Body";

export default {
  components: {
    Dashbord,
    Body
  },
};
</script>

