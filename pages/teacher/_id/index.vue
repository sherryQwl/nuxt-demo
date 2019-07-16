<template>
  <div class="detail">
    <!-- 这个id对应一个加了下划线的文件夹名 -->
    这是{{$route.params.id}}老师的详情信息
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  validate(data) {
    // console.log(data);
    // return /^\d+$/.test(obj.params.id);
    return true;
  }
};
</script>