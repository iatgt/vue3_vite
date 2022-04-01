<template>
  <div class="app-container">
    <el-container>
      <el-aside width="60%">
        <div class="demo-image">
          <div class="block">
            <span class="demonstration">示意图</span>
            <el-image style="width: 500px; height: 500px" :src="src" fit="scale-down"/>
          </div>
        </div>
      </el-aside>
      <el-main>
        <el-row>
          <el-card class="update-log">
            <template v-slot:header>
              <div class="clearfix">
                <span>全部集群总状态</span>
              </div>
            </template>
            <div class="body">
              <el-table :data="statusData" stripe border style="width: 100%">
                <el-table-column prop="completion" label="任务完成率" width="140" />
                <el-table-column prop="cost" label="当前总成本" width="140" />
                <el-table-column prop="loss" label="Agent损失率" width="140"/>
              </el-table>
            </div>
          </el-card>
        </el-row>
        <el-row>
          <el-card class="update-log">
            <template v-slot:header>
            <div class="clearfix">
              <span>Agent集群属性</span>
            </div>
          </template>
          <div class="body">
            <el-table :data="propData" stripe border style="width: 100%">
              <el-table-column prop="agentId" label="集群编号" width="210" />
              <el-table-column prop="agentProp" label="属性" width="210"/>
            </el-table>
          </div>
          </el-card>
        </el-row>
      </el-main>
    </el-container>
  </div>
</template>

<script setup name="Cluster">
  function goTarget(url) {
    window.open(url, '__blank')
  }
  const src = 'https://fuss10.elemecdn.com/a/3f/3302e58f9a181d2509f3dc0fa68b0jpeg.jpeg'
  const statusData = [
    {
      completion: '80%',
      cost: '80%',
      loss: '80%',
    },
  ]
  const propData = [
  {
    agentId: '集群1',
    agentProp: '集群1的属性',
  },
  {
    agentId: '集群2',
    agentProp: '集群2的属性',
  },
  {
    agentId: '集群3',
    agentProp: '集群3的属性',
  },
]
</script>
<style scoped lang="scss">
    .update-log {
        margin: 10px;
    }
    .demo-image .block {
    padding: 30px 0;
    text-align: center;
    border-right: solid 1px var(--el-border-color);
    display: inline-block;
    width: 20%;
    box-sizing: border-box;
    vertical-align: top;
    }
    .demo-image .block:last-child {
    border-right: none;
    }
    .demo-image .demonstration {
    display: block;
    // color: var(--el-text-color-secondary);
    font-size: 14px;
    margin-bottom: 20px;
    }
</style>