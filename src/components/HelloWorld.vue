<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="showModal=true">Show modal</button>
    <NewPostModal :show="showModal" @close="showModal = false" />
  </div>
</template>

<script>
import NewPostModal from "@/components/NewPostModal";
export default {
  name: "HelloWorld",
  components: {
    NewPostModal
  },
  props: {
    msg: String
  },
  data() {
    return {
      showModal: false
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
