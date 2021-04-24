<template>
  <div>
    <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
      <el-tab-pane label="经纬度转笛卡尔" name="first">
        <DegreesToCartesian></DegreesToCartesian>
      </el-tab-pane>
      <el-tab-pane label="笛卡尔转经纬度" name="second">
        <CartesianToDegrees></CartesianToDegrees>
      </el-tab-pane>
      <el-tab-pane label="经纬度转弧度" name="third">
        <DegreesToCartographic></DegreesToCartographic>
      </el-tab-pane>
      <el-tab-pane label="弧度转经纬度" name="fourth">
        <CartographicToDegrees></CartographicToDegrees>
      </el-tab-pane>
<!--      <el-tab-pane label="度分秒坐标转换" name="fifth">-->
<!--        <TransDuFenMiao></TransDuFenMiao>-->
<!--      </el-tab-pane>-->
    </el-tabs>
  </div>
</template>


<script>
import DegreesToCartesian from "@/components/transform/DegreesToCartesian";
import CartesianToDegrees from "@/components/transform/CartesianToDegrees";
import DegreesToCartographic from "@/components/transform/DegreesToCartographic";
// import TransDuFenMiao from "@/components/transform/TransDuFenMiao";
import CartographicToDegrees from "./CartographicToDegrees";
export default {
  name: "TransformTable",
  data() {
    return {
      activeName: 'first',
    }
  },
  components: {
    DegreesToCartesian,
    CartesianToDegrees,
    DegreesToCartographic,
    // TransDuFenMiao,
    CartographicToDegrees
  },
  methods: {
    handleClick(tab, event) {
      console.log(tab, event);
    },
  }
}
</script>

<style scoped>

</style>