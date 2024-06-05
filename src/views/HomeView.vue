<template>
  <div class="home">
    <div
      class="trigger_box"
      @mouseenter="showOrHideBox(true)"
      @mouseleave="showOrHideBox(false)"
    >
      <span>用鼠标hover我显示盒子</span>
      <div
      class="show_box"
      v-if="showboxKey"
    >
      <ul>
        <li
          v-for="item in lidata"
          :key="item.id"
        >{{ item.title }}</li>
      </ul>
    </div>
    </div>

    <div
      class="hover_trigger_box"
    >
      <span>纯csshover触发下面的盒子</span>
      <div
      class="hover_show_box"
    >
      <ul>
        <li
          v-for="item in lidata"
          :key="item.id"
        >{{ item.title }}</li>
      </ul>
    </div>
    </div>
    
  </div>
</template>

<script>
// @ is an alias to /src
const lidata = [
  {
    title: '这是我的元素1',
    id: 1
  },
  {
    title: '这是我的元素2',
    id: 2
  },
  {
    title: '这是我的元素3',
    id: 3
  },
  {
    title: '这是我的元素4',
    id: 4
  },
  {
    title: '这是我的元素5',
    id: 5
  }
];
export default {
  name: 'HomeView',
  data() {
    return {
      showboxKey: false,
      lidata
    };
  },
  created() {},
  methods: {
    showOrHideBox(flag) {
      this.showboxKey = flag;
      debugger
      console.log('这里显示了');
    }
  },
  components: {}
};
</script>
<style lang="less" scoped>
.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .trigger_box {
    position: relative;
    width: 200px;
    border: 1px solid #ccc;
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .show_box {
    position: absolute;
    bottom: -120px;
    left: 0;
    width: 300px;
    height: 120px;
    border: 1px solid #745353;
  }

  .hover_trigger_box{
    position: relative;
    margin-top: 200px;
    width: 200px;
    border: 1px solid #ccc;
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .hover_show_box{
    position: absolute;
    bottom: -120px;
    left: 0;
    width: 300px;
    height: 120px;
    border: 1px solid #745353;
    display: none;
  }
  .hover_trigger_box:hover .hover_show_box{
    display: block;
  }
}
</style>
