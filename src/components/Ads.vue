<template>
  <div class="Ads">
    <div class="AdBox_head">광고이름</div>
    <div class="AdBox_body">
      <div class="AdBox_body_thumbnail">이미지</div>
      <div class="AdBox_body_text">
        <div class="AdBox_body_text_title">광고제목</div>
        <div class="AdBox_body_text_content">광고내용</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="less">
@import "../styles/utils";

.Ads {
  display: flex;
  flex-direction: column;
  border: 1px solid #757575;
  width: 30rem;
  height: 10rem;
  margin-bottom: 2rem;
}
.AdBox_head {
}
.AdBox_body {
}
.AdBox_body_thumbnail {
}
.AdBox_body_text {
}
.AdBox_body_text_title {
}
.AdBox_body_text_content {
}
</style>

