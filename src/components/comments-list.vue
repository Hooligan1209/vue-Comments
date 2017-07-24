<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 v-show="comments.length===0">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <item v-for="(comment , index) in comments"
            :comment="comment"
            :index="index"
            :key="index"
            :delete-item="deleteItem"
      >

      </item>
    </ul>
  </div>
</template>

<script>
  import item from './comments-item.vue'

  export default {
      //声明接收哪些属性
      props: ['comments' , 'deleteItem'],
      components: {
          item
      }
  }
</script>

<style>
  .reply {
    margin-top: 0px;
  }

</style>
