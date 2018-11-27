<template>
  <div class="home text-600">
    <p>우측 상단에서</p>
    <p>페이지를 선택해 주세요.</p>
  </div>
</template>

<script>
    export default {
        name: "Home"
    }
</script>

<style lang="less">
@import '../styles/utils';
.home {
    text-align: center;
    padding: 12rem 1rem;
    p {
        margin: 1rem 0;
        font-size: 2rem;
        @media @mobile {
            font-size: 1.2rem;
        }
    }
}

</style>
