<template>
  <div class="wrapper" :style="{ '--accordioncolor': color }">
    <div class="accordion" @click="toggleItem">
      <h2 class="title">
        <slot name="title"></slot>
      </h2>
      <div v-if="!show" class="plus">+</div>
      <div v-else class="minus">-</div>
    </div>
    <div v-show="show" class="content">
      <slot name="content"></slot>
    </div>
  </div>
</template>
<script>
export default {
  props: ['color'],
  data: function() {
    return {
      show: false
    };
  },
  methods: {
    toggleItem: function() {
      this.show = !this.show;
    }
  }
};
</script>
<style scoped>
:root {
  --accordioncolorcolor: #00ADEE;
}
.wrapper {
  margin: 0 auto;
  background: var(--accordioncolor);
  font-family: "Arial Rounded MT Bold";
}
.accordion {
  display: flex;
  cursor: pointer;
  margin: 0;
  padding: 40px 40px;
  display: flex;
  justify-content: space-between;
  color: white;
}
.plus,
.minus {
  font-size: 1.4rem;
}
.title {
  color: white;
  font-size: 1.2rem;
}
.content {
  text-align: left;
  width: 100%;
  background: white;
  padding: 40px 40px;
}
</style>
