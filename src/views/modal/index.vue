<template>
  <div style="padding: 24px;">
    <el-row style="margin-bottom: 20px;">
      <el-col>
        <el-button @click="openDialog(true)">
          Dialog Appended To Body
        </el-button>
        <el-button @click="openDialog(false)">
          Dialog Appended To Parent Node
        </el-button>
      </el-col>
    </el-row>
    <el-row>
      <el-col>
        <el-button @click="openDrawer(true)">
          Drawer Appended To Body
        </el-button>
        <el-button @click="openDrawer(false)">
          Drawer Appended To Parent Node
        </el-button>
      </el-col>
    </el-row>
    <el-dialog
      title="Modal Dialog"
      :visible.sync="showDialog"
      :modal-append-to-body="appendToBody"
      width="40%"
    >
      <p>
        This is a dialog with modal appended to {{ appendToBody ? 'body' : 'it\'s parent.node' }}.<br /><br />
        这是一个模态对话框，遮罩层插入至 {{ appendToBody ? 'body' : 'Dialog的父元素上' }}
      </p>
      <div slot="footer" class="dialog-footer">
        <el-button @click="showDialog=false">取 消</el-button>
        <el-button type="primary" @click="showDialog=false">确 定</el-button>
      </div>
    </el-dialog>

    <el-drawer
      title="Drawer"
      :visible.sync="showDrawer"
      :append-to-body="false"
      :destroy-on-close="true"
      direction="rtl"
    />
    <el-drawer
      title="Drawer"
      :visible.sync="showBodyDrawer"
      :append-to-body="true"
      :destroy-on-close="true"
      direction="rtl"
    />
  </div>
</template>

<script>
export default {
  name: 'Modal',
  data() {
    return {
      showDialog: false,
      appendToBody: false,
      showBodyDrawer: false,
      showDrawer: false
    }
  },
  methods: {
    openDialog(appendToBody) {
      this.appendToBody = appendToBody
      this.showDialog = true
    },
    openDrawer(appendToBody) {
      if (appendToBody) {
        this.showBodyDrawer = true
      } else {
        this.showDrawer = true
      }
    }
  }
}
</script>

<style>
.el-dialog__wrapper {
  position: absolute;
}

.v-modal {
  position: absolute;
}
</style>
