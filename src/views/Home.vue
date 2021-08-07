<template>
  <div>
    <Banner/>
    <AboutMe class="mt-5"/>
  </div>
</template>
<script>
// @ is an alias to /src

import Banner from "../components/Banner";
import AboutMe from "../components/AboutMe";
export default {
  name: 'Home',
  components: {AboutMe, Banner},
}
</script>