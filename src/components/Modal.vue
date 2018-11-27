<template>
  <div v-bind:="showModal" class="Modal_back">
    <div class="Modal_form">
      <span class="Modal_title">필터</span>
      <div class="category_list">
        <span>
          <input v-model="category" type="radio" id="apple" name="category" value="1">
          <label for="apple">apple</label>
        </span>
        <span>
          <input v-model="category" type="radio" id="banana" name="category" value="2">
          <label for="banana">banana</label>
        </span>
        <span>
          <input v-model="category" type="radio" id="coconut" name="category" value="3">
          <label for="coconut">coconut</label>
        </span>
      </div>
      <button class="Modal_btn_save" @click="$emit('change', category)">저장</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      category: ""
    };
  }
};
</script>

<style lang="less">
@import "../styles/utils";

.Modal_back {
  position: fixed;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 20;
  background-color: rgba(0, 0, 0, 0.7);

  &.hidden {
    display: none;
  }
}
.Modal_form {
  display: flex;
  flex-direction: column;
  width: 30rem;
  padding: 1rem;
  background-color: white;
  font-size: 1.2rem;

  .Modal_title {
    font-size: 1.5rem;
  }
  @media @mobile {
    width: 20rem;
  }
}
.category_list {
  margin-top: 0.7rem;
  margin-bottom: 0.7rem;

  span {
    margin-right: 0.7rem;
  }
}
.Modal_btn_save {
  width: 4.3rem;
  font-size: 1rem;
  align-self: flex-end;
}
</style>