<template>
  <div class="tab">
    <div class="tab-header">
      <h2>Our Product</h2>
      <p>Accumsan vitae pede lacus ut ullamcorper sollicitudin quisque libero</p>
    </div>
    <div class="tab-body">
      <div class="tab-buttons">
        <button @click="activateTab('tab1')" :class="{ active: activeTab === 'tab1' }">
          Tab 1
        </button>
        <button @click="activateTab('tab2')" :class="{ active: activeTab === 'tab2' }">
          Tab 2
        </button>
        <button @click="activateTab('tab3')" :class="{ active: activeTab === 'tab3' }">
          Tab 3
        </button>
      </div>
      <div class="tab-contents">
        <div v-if="activeTab === 'tab1'">
          <p>Content for Tab 1 goes here.</p>
        </div>
        <div v-if="activeTab === 'tab2'">
          <p>Content for Tab 2 goes here.</p>
        </div>
        <div v-if="activeTab === 'tab3'">
          <p>Content for Tab 3 goes here.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 'tab1'
    }
  },
  methods: {
    activateTab(tab) {
      this.activeTab = tab
    }
  }
}
</script>

<style lang="scss" scoped>
.tab {
  h2 {
    text-align: center;
    font-family: roboto_med;
  }

  p {
    text-align: center;
    font-family: roboto_light;
    font-style: italic;
    color: rgba(0, 0, 0, 0.623);
  }
  .tab-buttons {
    display: flex;
    margin-bottom: 10px;
  }

  .tab-buttons button {
    padding: 10px 15px;
    border: 1px solid #ccc;
    background-color: #f2f2f2;
    cursor: pointer;
  }

  .tab-buttons button.active {
    background-color: #007bff;
    color: #fff;
  }

  .tab-buttons button:hover {
    background-color: #007bff;
    color: #fff;
  }
}
</style>
