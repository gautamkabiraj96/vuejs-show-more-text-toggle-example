<template>
  <div id="app">
    <p>
      {{ displayedContent }}
    </p>
    <p class="toggle-color" @click="expandContent" v-if="isCollapsed">
      Show more
    </p>
    <p class="toggle-color" @click="collapseContent(700)" v-else>Show less</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      content:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla egestas lacinia augue in pharetra. Quisque viverra maximus lacus vel pharetra. Vestibulum id posuere sapien, vel molestie est. Maecenas dignissim libero fringilla diam euismod congue. Praesent ut tellus ligula. Curabitur interdum sem ut purus vehicula, et accumsan erat ornare. Nullam convallis sollicitudin tempus. Donec vitae tincidunt tellus. Fusce rhoncus nulla sed lectus mattis, in aliquet libero fringilla. Cras vestibulum gravida sodales. Praesent sit amet mi venenatis, rhoncus eros quis, fermentum lacus. Morbi sed iaculis leo. Maecenas sed vestibulum mi, id consectetur erat. Duis cursus odio nec odio rutrum, rhoncus luctus sapien auctor. Integer diam urna, ultricies ac ultrices eget, cursus sed purus. Sed sit amet cursus velit. Vivamus sem lectus, dignissim eget enim et, placerat tempor est. Vivamus ut velit sed nibh suscipit tempus vitae non tellus. Praesent ut dui sit amet libero tincidunt volutpat vitae ac urna. Donec pharetra dolor sapien, sed suscipit mi laoreet sit amet. Maecenas cursus dictum urna. Praesent ornare mauris in ultricies euismod. Mauris molestie, nisl consectetur facilisis suscipit, turpis nibh congue purus, id pretium velit sapien ac metus.",
      displayedContent: "",
      isCollapsed: false,
    };
  },
  mounted() {
    this.collapseContent(700);
  },
  methods: {
    collapseContent(shortenSize = 100) {
      this.displayedContent = this.content.slice(0, shortenSize);
      this.isCollapsed = !this.isCollapsed;
    },
    expandContent() {
      this.displayedContent = this.content;
      this.isCollapsed = !this.isCollapsed;
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  margin-top: 60px;
  padding: 20px;
}
.toggle-color {
  color: rgb(0, 89, 255);
  font-weight: 600;
  cursor: pointer;
}
</style>
