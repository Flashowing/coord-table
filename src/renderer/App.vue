<template>
  <div id="app">
    <el-container>
      <el-header>
        <el-row>
          <el-col :md="6" class="hidden-xs-only">
            <div style="color: white">placeholder</div>
          </el-col>
          <el-col :md="12" :xs="24">
            <Header/>
          </el-col>
        </el-row>
      </el-header>
      <el-main>
        <el-row>
          <el-col :md="6">
            <div style="color: white">placeholder</div>
          </el-col>
          <el-col :md="12">
            <div class="map">
              <CesiumViewer></CesiumViewer>
            </div>
          </el-col>
        </el-row>
        <el-row>
          <el-col :md="6" class="hidden-xs-only">
            <div style="color: white">placeholder</div>
          </el-col>
          <el-col :md="12" :xs="24">
            <TransformTable></TransformTable>
          </el-col>
        </el-row>
      </el-main>
    </el-container>
  </div>
</template>

<script>
import CesiumViewer from "./components/CesiumViewer";
import Header from "./components/Header";
import TransformTable from "./components/transform/TransformTable";

  export default {
    name: 'coord',
    components:{
      CesiumViewer,
      Header,
      TransformTable
    }
  }
</script>

<style>
  /* CSS */
</style>
