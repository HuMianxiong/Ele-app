<template>
  <div class="addAddress">
    <Header :isLeft="true" :title="title" />
    <!-- 添加地址 -->
    <div class="viewbody">
      <div class="content">
        <FormBlock label="联系人" placeholder="姓名" />
        <FormBlock label="电话" placeholder="手机号码" />
        <FormBlock label="地址" placeholder="小区/写字楼/学校等" icon="angle-right" />

        <FormBlock label="门牌号" placeholder="10号楼5单元404" icon="edit" textarea="textarea" />
      </div>
    </div>
  </div>
</template>

<script>
import Header from "../../components/Header";
import FormBlock from "../../components/Orders/FormBlock";
export default {
  name: "AddAddress",
  components: {
    Header,
    FormBlock
  },
  data() {
    return {
      title: "添加地址"
    };
  }
};
</script>

<style scoped>
.addAddress {
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  padding-top: 45px;
}
.viewbody {
  width: 100%;
  height: 100%;
  overflow: auto;
  box-sizing: border-box;
  background-color: #f5f5f5;
}
.content {
  padding-left: 4vw;
  background: #fff;
  font-size: 0.94rem;
}
</style>