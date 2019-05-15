<template>
  <div>
    <v-content>
    <MyPage :title="page1" :titleEnglish="titleEnglish1" @childObject="setObject"/>
    <MyPage :title="page2" :titleEnglish="titleEnglish2" @childObject="setObject"/>
    <MyPage :title="page3" :titleEnglish="titleEnglish3" @childObject="setObject"/>
    <MyPage :title="page4" :titleEnglish="titleEnglish4" @childObject="setObject"/>

    <p></p>
    <p>현재 선택된 화면 : {{display}}</p>
      <router-view/>
    </v-content>
  </div>
</template>

<script>
import MyPage from "./components/MyPage";
import { stringify } from "querystring";

export default {
  name: "App",
  components: {
    MyPage
  },
  data() {
    return {
      page1: "홈",
      page2: "마이페이지",
      page3: "서비스",
      page4: "로그인",
      titleEnglish1: "home",
      titleEnglish2: "myPage",
      titleEnglish3: "service",
      titleEnglish4: "login",

      display: "home"
    };
  },
  methods: {
    setObject(object) {
      this.display = JSON.stringify(object);
    }
  }
};
</script>
