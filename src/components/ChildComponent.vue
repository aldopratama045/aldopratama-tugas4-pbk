<template>
  <div class="child-container">
    <h2 class="title">Child Component</h2>
    <button class="send-button" @click="emitData">Click Me!</button>
    <div class="slot-wrapper">
      <slot :slotData="slotData"></slot>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slotData: 'dan Inilah data from child'
    };
  },
  methods: {
    emitData() {
      this.$emit('data-updated', this.slotData);
    }
  }
};
</script>

<style scoped>
.child-container {
  text-align: center;
  margin: 20px auto;
  padding: 20px;
  border-radius: 10px;
  background-color: #f0f0f0;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.child-container:hover {
  transform: translateY(-5px);
}

.title {
  font-size: 28px;
  margin-bottom: 20px;
  color: #333;
}

.send-button {
  background-color: #4caf50;
  color: #fff;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s ease;
}

.send-button:hover {
  background-color: #45a049;
}

.slot-wrapper {
  margin-top: 20px;
  border-top: 2px solid #4caf50;
  padding-top: 20px;
  color: #666;
  font-size: 18px;
}
</style>
