
<template>
  <div>
    <div class="MainSection">
      <!-- <Ads/> -->
      <div class="Main_head">
        <button class="Main_btn_filter" v-on:click="showModal = true">필터</button>
        <div class="Main_head_sortBtns">
          <span @click="sortAsc">오름차순</span>
          <span @click="sortDesc">내림차순</span>
        </div>
      </div>
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
import Ads from "@/components/Ads";

export default {
  mounted() {
    window
      .$(".Main_head_sortBtns")
      .find("span")
      .click(e => {
        window
          .$(".Main_head_sortBtns")
          .find("span")
          .removeClass("active");
        window.$(e.target).addClass("active");
      });
  },
  components: { Modal, Post, Ads },
  data() {
    return {
      showModal: false,
      datas: null,
      categoryName: null,
      adData: null
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
    },
    sortAsc() {
      if (this.datas) {
        this.datas.sort((a, b) => {
          return a.no - b.no;
        });
      }
    },
    sortDesc() {
      if (this.datas) {
        this.datas.sort((a, b) => {
          return b.no - a.no;
        });
      }
    }
  }
};
</script>

<style lang="less">
@import "../styles/utils";

.MainSection {
  margin: 2.5rem 2rem;

  @media @mobile {
    margin: 1.5rem 0.875rem;
  }
}
.Main_head {
  display: flex;
  justify-content: space-between;
  width: 30rem;

  @media @mobile {
    width: 100%;
  }
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
.Main_head_sortBtns {
  display: flex;
  justify-content: space-between;
  align-self: flex-end;
  height: fit-content;
  width: 8rem;

  .active {
    color: #ef5350;
  }
  span:hover {
    cursor: pointer;
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