
<template>
  <div>
    <div class="MainSection">
      <button class="Main_btn_filter" v-on:click="showModal = true">필터</button>
      <div v-if="categoryName !== null" class="Main_postList">
        <Post v-for="data in datas" :key="data.no" :data="data" :categoryName="categoryName"/>
      </div>
    </div>
    <Modal :class="showModal ? '' : 'hidden'" @change="changeCategory"/>
  </div>
</template>

<script>
import Modal from "@/components/Modal";
import axios from "axios";
import Post from "@/components/Post";

export default {
  components: { Modal, Post },
  data() {
    return {
      showModal: false,
      datas: null,
      categoryName: null
    };
  },
  methods: {
    async changeCategory(category) {
      await axios
        .get(
          "http://comento.cafe24.com/request.php?page=1&ord=asc&category=" +
            category
        )
        .then(res => {
          this.datas = res.data.list;
          this.showModal = false;
          console.log(res.data.list);
        });

      await axios.get("http://comento.cafe24.com/category.php").then(res => {
        const data = res.data.list;
        for (let i = 0; i < data.length; i++) {
          console.log(data[i]);
          if (data[i].no == category) {
            console.log("ㅗㅜㅑ");
            this.categoryName = data[i].name;
          }
        }
      });
    }
  }
};
</script>

<style lang="less">
.MainSection {
  margin: 2.5rem 2rem;
}
.Main_btn_filter {
  background-color: #00c854;
  border: 0;
  padding: 0.3rem 0.7rem;
  font-size: 1.3rem;
  color: white;

  &:hover {
    cursor: pointer;
  }
  &:focus {
    outline: none;
  }
}
.Main_modal {
  position: fixed;
  width: 100%;
  height: 100%;
  &.hidden {
    display: none;
  }
}
</style>