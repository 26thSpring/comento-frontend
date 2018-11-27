<template>
  <div class="Navbar">
    <router-link to="/" class="Navbar_title">
      <span class="logo_title text-500">코멘토</span> 프론트엔드 박찬욱
    </router-link>
    <div class="Navbar_links text-400">
      <router-link to="/main">와이어프레임 1</router-link>
      <router-link to="/detail">와이어프레임 2</router-link>
    </div>
  </div>
</template>

<style lang="less">
@import "../styles/utils";

.Navbar {
  position: fixed;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 5rem;
  padding: 0 2rem;
  background-color: #fafafa;
  color: gray;
  z-index: 10;
  box-shadow: 0px 0px 3px 0px rgba(0, 0, 0, 0.15);
}
.Navbar_title {
  font-size: 1.7rem;
  font-weight: 300;
  .logo_title {
    color: #00c854;
  }
  @media @mobile {
    font-size: 1.6rem;
  }
}

.Navbar_links {
  font-size: 1.2rem;
  a {
    margin-right: 0.6rem;
  }
  .router-link-active {
    color: #00c854;
  }
  @media @mobile {
    font-size: 1.1rem;
  }
}
</style>
