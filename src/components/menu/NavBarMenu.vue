<template>
  <div>
    <nav class="navbar navbar-expand NavBar_shi">
      <!--      <a class="navbar-brand">預留網站名字</a>-->
      <a class="navbar-brand"></a>
      <div class="navbar-nav mr-auto">
        <li class="nav-item   ">
          <router-link to="/ProjectHome" class="nav-link">
            <font-awesome-icon class="TheSameFontColor" icon="home"/>
            <a class="TheSameFontColor">主頁</a>
          </router-link>
        </li>
        <li class="nav-item mt-1">
          <b-button pill size="sm" variant="outline-secondary" v-b-toggle.sidebar-1>各項選單</b-button>
        </li>
        <li>
          <router-link to="/In02">
            <b-button
                class="ml-2 mt-1" pill size="sm" variant="outline-secondary"
            >快速查詢

            </b-button>
          </router-link>
        </li>
        <li>
          <router-link to="/In01">
            <b-button
                class="ml-2 mt-1" pill size="sm" variant="outline-secondary"
            >快速新增
            </b-button>
          </router-link>
        </li>
        <li>
          <b-button
              class="ml-2 mt-1" pill size="sm" variant="outline-secondary"
              @click="test()">跟後端測試按鈕
          </b-button>

        </li>
      </div>

      <div class="navbar-nav ml-auto">

        <li class="nav-item dropdown mt-1 mr-1">

          <b-button pill size="sm" variant="outline-secondary" v-b-toggle.sidebar-person>
            <b-icon v-if="false" icon=" person-lines-fill"></b-icon>
            個人中心
          </b-button>
        </li>
        <li class="nav-item ">
          <a class="nav-link TheSameFontColor">
            <font-awesome-icon icon="sign-out-alt"/>
            LogOut
          </a>
        </li>
      </div>

    </nav>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "navBarMenu",
  setup() {
    const test = () => {
      const API_URL = 'http://localhost:8070/api/auth/helloWord';

      axios.get(API_URL)
          .then((res) => {
            console.log('res:', res);

            let strs =res.status === 200?'成功':'失敗'
            alert( strs )
          })

    }
    return {test}
  }
}
</script>

<style>
.NavBar_shi {
  background-color: rgb(0, 0, 0) !important;
  box-shadow: none;
  border-bottom: 1px solid #ddd;

}

.TheSameFontColor {
  color: #66615B;
}

</style>