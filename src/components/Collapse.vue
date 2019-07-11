<template>
  <div class="v-collapse">
    <div class="v-collapse-header" :style="{backgroundColor: bgc}" @click="openCollapse">
      <div>{{ title }}</div>
      <div>
        <span :class="[{'up': open, 'down': !open}, 'v-arrow']"></span>
      </div>
    </div>
    <transition name="slide">
      <div v-if="open" class="v-collapse-body">
        <slot></slot>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "Collapse",
  props: {
    title: {
      required: true
    },
    bgc: {
      required: true
    }
  },
  data() {
    return {
      open: false
    };
  },
  methods: {
    openCollapse() {
      this.open = !this.open;
    }
  }
};
</script>

<style scoped>
.v-collapse {
  margin-bottom: 20px;
}

.v-collapse-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 25px;
  color: #fff;
  font-size: 18px;
  font-weight: bold;
  cursor: pointer;
}

.v-arrow {
  display: inline-block;
  width: 20px;
  height: 20px;
  background: transparent;
  text-indent: -9999px;
  border-top: 3px solid #fff;
  border-left: 3px solid #fff;
  transition: all 250ms ease-in-out;
  text-decoration: none;
  color: transparent;
}

.v-arrow::before {
  display: block;
  height: 200%;
  width: 200%;
  margin-left: -50%;
  margin-top: -50%;
  content: "";
  transform: rotate(45deg);
}

.v-arrow.down {
  transform: rotate(-135deg);
}

.v-arrow.up {
  transform: rotate(45deg);
}

.v-collapse-body {
  border: 1px solid #ccc;
}

.slide-enter-active {
  transition-duration: 0.3s;
  transition-timing-function: ease-in;
}

.slide-leave-active {
  transition-duration: 0.3s;
  transition-timing-function: cubic-bezier(0, 1, 0.5, 1);
}

.slide-enter-to,
.slide-leave {
  max-height: 200px;
  overflow-y: hidden;
}

.slide-enter,
.slide-leave-to {
  overflow: hidden;
  max-height: 0;
}
</style>
