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
  props: ["data", "categoryName"]
};
</script>

<style lang="less">
@import "../styles/utils";

.Post {
  display: flex;
  flex-direction: column;
  width: 30rem;
  height: 10rem;
  border: 2px solid #757575;
  margin: 0.875rem 0;

  @media @mobile {
    width: 100%;
    height: 9.5rem;
    margin: 0.875rem 0;
  }
}
.Post_header {
  border: 0px solid #757575;
  border-bottom-width: 2px;
  padding: 0.5rem;
  &_categoryName {
    float: left;
  }
  &_postNo {
    float: right;
  }
  @media @mobile {
    font-size: 0.85rem;
  }
}

.Post_body {
  flex: 1 0 0;
  display: flex;
  flex-direction: column;
  padding: 0.5rem;
}
.Post_info {
  &_email {
    display: inline;
    margin-right: 0.3rem;
  }
  &_regdate {
    display: inline;
    margin-left: 0.3rem;
  }
  @media @mobile {
    font-size: 0.85rem;
  }
}
.Post_value {
  margin-top: 1rem;
  &_title {
    font-size: 1.2rem;
    font-weight: 600;
    display: -webkit-box;
    -webkit-line-clamp: 1;
    -webkit-box-orient: vertical;
    overflow: hidden;
    word-break: break-all;
  }
  &_content {
    display: -webkit-box;
    -webkit-line-clamp: 1;
    -webkit-box-orient: vertical;
    overflow: hidden;
    word-break: break-all;
  }
}
</style>