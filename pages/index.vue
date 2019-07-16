<template>
  <div class="container">
    <nuxt-link to="/study">跳转到study页面</nuxt-link>
    <button @click="jumpTo">跳转到study页面</button>
    <el-button>测试element</el-button>
    <div>
      <ul>
        <li v-for="item in movieList" :key="item.id">{{item.title}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";

export default {
  data() {
    return {
      // movieList: [
      //   { title: "肖生克的救赎", id: 1 },
      //   { title: "大圣归来", id: 1 },
      //   { title: "当幸福来敲门", id: 1 }
      // ]
    };
  },
  components: {
    Logo
  },
  // 发送异步请求，在asyncData函数中发送
  // asyncData(context, callback) {
  //   setTimeout(() => {
  //     // callback有两个参数，第一个是错误对象，第二个是数据对象
  //     callback(null, {
  //       movieList: [
  //         { title: "肖生克的救赎", id: 1 },
  //         { title: "大圣归来", id: 1 },
  //         { title: "当幸福来敲门", id: 1 }
  //       ]
  //     });
  //   },1000);
  // },
  asyncData(context, callback) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          movieList: [
            { title: "肖生克的救赎2", id: 1 },
            { title: "大圣归来2", id: 1 },
            { title: "当幸福来敲2", id: 1 }
          ]
        });
      }, 1000);
    })
    .then(data => {
      console.log(data);
      callback(null, {
        movieList:data.movieList
      })
    })
    .catch(err => {
      callback(err);
      // context.error(err);
    });
  },
  methods: {
    jumpTo() {
      // this.$router.push({name:"study"});
      // this.$router.push("/study");
      this.$router.push({ path: "/study" });
    }
  }
};
</script>

<style>
</style>
