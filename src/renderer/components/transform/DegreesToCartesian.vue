<template>
  <div>
    <el-row>
      <el-col :span="24">
        <div class="grid-content bg-purple">Cesium.Cartesian3.fromDegrees (longitude, latitude, height , ellipsoid ,
          result )
        </div>
      </el-col>
    </el-row>
    <el-row>
      <table>
        <tr>
          <td>经度(longitude):</td>
          <td>
            <el-col :span="6" :xs="24">
              <div class="grid-content bg-purple">
                <el-input class="input" v-model="lon_input" placeholder="请输入经度"></el-input>
              </div>
            </el-col>
          </td>
        </tr>
        <tr>
          <td>纬度(latitude):</td>
          <td>
            <el-col :span="6" :xs="24">
              <div class="grid-content bg-purple">
                <el-input class="input" v-model="lat_input" placeholder="请输入纬度"></el-input>
              </div>
            </el-col>
          </td>
        </tr>
        <tr>
          <td colspan="2">{{ result }}</td>
        </tr>
        <tr>
          <td>
            <el-link id="copy-f3" class="copy-f3" v-clipboard:copy="result" v-clipboard:success="onCopy"
                     v-clipboard:error="onError" v-show="showCopy" :underline="false" type="primary"
                     icon="el-icon-document-copy">复制
            </el-link>
          </td>
        </tr>
        <tr>
          <td colspan="2">
            <el-button @click="LatAndLonToCartesian">转换</el-button>
          </td>
        </tr>
      </table>
    </el-row>
  </div>

</template>

<script>
import * as Cesium from "cesium";
export default {
  name: "DegreesToCartesian",
  data() {
    return {
      lon_input: '',
      lat_input: '',
      result: '',
      showCopy: false,
    }
  },
  methods: {
    LatAndLonToCartesian: function () {
      try {
        var longitude = Number(this.lon_input);
        var latitude = Number(this.lat_input);
        let cartesian3 = Cesium.Cartesian3.fromDegrees(longitude, latitude);
        this.result = cartesian3;
        this.showCopy = true;
      } catch (e) {
        console.log(e);
        this.$message.error('请输入正确的坐标');
      }
    },
    onCopy: function () {
      this.$message.success('复制成功')
    },
    onError: function () {
      this.$message.error('复制失败');
    }
  }
}
</script>

<style scoped>

.input {
  width: 200px;
}
</style>