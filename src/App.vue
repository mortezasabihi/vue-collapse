<template>
  <div id="body">
    <h1>
      <span>Vue</span> Accordion
    </h1>

    <collapse title="About vue js" bgc="red">
      <div class="my-content">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur sit laborum et nisi recusandae voluptas cumque itaque laboriosam inventore rerum quae nihil, odio culpa eum nemo dicta, debitis ipsum ipsam.</p>
      </div>
    </collapse>

    <collapse title="About react js" bgc="green">
      <div class="my-content">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur sit laborum et nisi recusandae voluptas cumque itaque laboriosam inventore rerum quae nihil, odio culpa eum nemo dicta, debitis ipsum ipsam.</p>
      </div>
    </collapse>
  </div>
</template>

<script>
import collapse from "./components/Collapse";

export default {
  name: "app",
  components: {
    collapse
  }
};
</script>

<style>
body {
  overflow-y: auto;
  font-family: "Open Sans", sans-serif;
}

#body {
  width: 80%;
  margin: 0 auto;
}

h1 {
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 3px;
  margin: 50px 0 80px 0;
}

h1 span {
  color: #42b883;
}

.my-content {
  padding: 20px;
}
</style>
