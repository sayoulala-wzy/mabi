<template>
  <div>
    <a-modal
      title="设置提醒"
      width="50%"
      footer=""
      :visible="true"
      :confirm-loading="confirmLoading"
      @ok="handleOk"
      @cancel="handleCancel"
    >
      <p>
        永不
        <!-- <a-checkbox @change="onChange"> </a-checkbox> -->
      </p>
      <a-divider />
      <p>每天</p>
      <a-divider />
      <p>每周</p>
      <a-divider />
      <p>每月</p>
      <a-divider />
      <p>每年</p>
      <a-divider />
      <p>
        自定义
        <a-input placeholder="年" style="width: 50px; margin-left: 6%" />
        <a-input placeholder="月" style="width: 50px; margin-left: 6%" />
        <a-input placeholder="日" style="width: 50px; margin-left: 6%" />
        <a-input placeholder="时" style="width: 50px; margin-left: 6%" />
        <a-input placeholder="分" style="width: 50px; margin-left: 6%" />
      </p>
      <a-divider />
      <p>
        <a-button
          type="primary"
          style="width: auto;background-color: #25A47C; width :50%;margin-left: 25%;"
        >
          保存
        </a-button>
      </p>
    </a-modal>
  </div>
</template>
<script>
export default {
  data() {
    return {
      ModalText: "Content of the modal",
      visible: false,
      confirmLoading: false
    };
  },
  methods: {
    showModal() {
      this.visible = true;
    },
    handleOk(e) {
      this.ModalText = "The modal will be closed after two seconds";
      this.confirmLoading = true;
      setTimeout(() => {
        this.visible = false;
        this.confirmLoading = false;
      }, 2000);
    },
    handleCancel(e) {
      console.log("Clicked cancel button");
      this.visible = false;
    }
  }
};
</script>
<script></script>
