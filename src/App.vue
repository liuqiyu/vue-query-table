<template>
  <div id="app">
    <VueQueryTable :config="config"></VueQueryTable>
  </div>
</template>

<script>
import VueQueryTable from './components'

export default {
  name: 'App',
  components: {
    VueQueryTable
  },
  data () {
    return {
      config: {
        http: {},
        options: {},
        columns: [],
        operation: {
          fixed: 'right',
          label: '操作',
          width: '150px',
          options: [
            {
              label: '编辑',
              icon: 'el-icon-edit-outline',
              type: 'icon',
              func: row => this.handleUpdate(row)
            },
            {
              label: '删除',
              icon: 'iconfont iconshanchu',
              type: 'icon',
              func: row => this.handleDelete(row)
            }
          ]
        },
        formatter: {}
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
