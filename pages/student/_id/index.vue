<template>
  <div class="stu-detail">
    <!-- 这个id对应一个加了下划线的文件夹名 -->
    这是{{$route.params.id}}号学生的详情信息
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  validate(data) {
    console.log(data);
    // return /^\d+$/.test(obj.params.id);
  }
};
</script>