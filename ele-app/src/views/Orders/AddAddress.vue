<template>
  <div class="addAddress">
    <Header :isLeft="true" :title="title" />
    <!-- 添加地址 -->
    <div class="viewbody">
      <div class="content">
        <FormBlock
          label="联系人"
          placeholder="姓名"
          :tags="sexes"
          @checkSex="checkSex"
          :sex="addressInfo.sex"
          v-model="addressInfo.name"
        />
        <FormBlock label="电话" placeholder="手机号码" v-model="addressInfo.phone" />
        <FormBlock
          v-model="addressInfo.address"
          label="地址"
          placeholder="小区/写字楼/学校等"
          icon="angle-right"
          @click="showSearch=true"
        />

        <FormBlock
          v-model="addressInfo.bottom"
          label="门牌号"
          placeholder="10号楼5单元404"
          icon="edit"
          textarea="textarea"
        />
        <div class="formblock">
          <div class="label-wrap">标签</div>
          <TabTag :tags="tags" @checkTag="checkTag" :selectTag="addressInfo.tag"></TabTag>
        </div>
      </div>
    </div>
    <!-- 搜素地址 -->
    <AddressSearch :showSearch="showSearch" @close="showSearch=false" :addressInfo="addressInfo" />
  </div>
</template>

<script>
import Header from "../../components/Header";
import FormBlock from "../../components/Orders/FormBlock";
import TabTag from "../../components/Orders/TabTag";
import AddressSearch from "../../views/Orders/AddressSearch";
export default {
  name: "AddAddress",
  components: {
    Header,
    FormBlock,
    TabTag,
    AddressSearch
  },
  data() {
    return {
      title: "添加地址",
      tags: ["家", "学校", "公司"],
      sexes: ["先生", "女士"],
      addressInfo: {
        tag: "",
        sex: "",
        address: "",
        name: "",
        phone: "",
        bottom: ""
      },
      showSearch: false
    };
  },
  methods: {
    checkTag(item) {
      //   console.log(item);
      this.addressInfo.tag = item;
    },
    checkSex(item) {
      console.log(item);
      this.addressInfo.sex = item;
    }
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
.formblock {
  background-color: #fff;
  border-bottom: 1px solid #eee;
  display: flex;
}
.formblock .label-wrap {
  flex-basis: 17.333333vw;
  padding: 3.733333vw 0;
  line-height: 4.8vw;
  color: #333;
  font-weight: 700;
}
</style>