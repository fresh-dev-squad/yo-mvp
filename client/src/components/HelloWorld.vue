<template>
  <div class="hello">
    <button @click="pingLocation()">yo</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  methods: {
    pingLocation() {
      const success = position => {
        const coordinates = position.coords;

        console.log("Your current position is:");
        console.log(`Latitude : ${coordinates.latitude}`);
        console.log(`Longitude: ${coordinates.longitude}`);
      };

      const failure = err => {
        console.warn(`ERROR(${err.code}): ${err.message}`);
      };

      navigator.geolocation.getCurrentPosition(success, failure);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
