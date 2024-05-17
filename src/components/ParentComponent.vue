<template>
  <div class="parent-container">
    <h1 class="title">Parent Component</h1>
    <ChildComponent @data-updated="updateDataFromChild">
      <template v-slot:default="slotProps">
        <div class="slot-content">
          <p>Data dari slot: {{ slotProps.slotData }}</p>
        </div>
      </template>
    </ChildComponent>
    <p class="child-data">Data dari komponen child: {{ dataFromChild }}</p>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  components: {
    ChildComponent
  },
  data() {
    return {
      dataFromChild: ''
    };
  },
  methods: {
    updateDataFromChild(data) {
      this.dataFromChild = data;
    }
  }
};
</script>

<style scoped>
.parent-container {
  margin: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  background-color: #5DEBD7;
}

.title {
  color: #874CCC;
  font-family: 'Arial, sans-serif';
  margin-bottom: 16px;
}

.slot-content {
  background-color: #e7f3fe;
  padding: 10px;
  border: 1px solid #b3d4fc;
  border-radius: 4px;
  margin-bottom: 16px;
}

.child-data {
  color: #555;
  font-family: 'Arial, sans-serif';
}
</style>
