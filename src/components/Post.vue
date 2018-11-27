<template>
  <div class="Post">
    <div class="Post_header">
      <span class="Post_header_categoryName">{{categoryName}}</span>
      <span class="Post_header_postNo">{{data.no}}</span>
    </div>
    <div class="Post_body">
      <div class="Post_info">
        <div class="Post_info_email">{{data.email}}</div>&nbsp;|&nbsp;
        <div class="Post_info_regdate">{{data.updated_at}}</div>
      </div>
      <div class="Post_value">
        <div class="Post_value_title">{{data.title}}</div>
        <div class="Post_value_content">{{data.contents}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  created() {
    console.log(this.categoryName);
  },
  data() {
    return {};
  },
  props: ["data", "categoryName"]
};
</script>

<style lang="less">
.Post {
  display: flex;
  flex-direction: column;
  width: 30rem;
  border: 2px solid #757575;
  margin: 0.875rem 0;
}
.Post_header {
  &_categoryName {
    float: left;
  }
  &_postNo {
    float: right;
  }
}

.Post_body {
  margin-top: 0.5rem;
}
.Post_info {
  display: flex;
  &_email {
    margin-right: 0.3rem;
  }
  &_regdate {
    margin-left: 0.3rem;
  }
}
.Post_value {
}
.Post_value_title {
}
.Post_value_content {
}
</style>