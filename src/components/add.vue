<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" class="form-control" placeholder="用户名" v-model="username">
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea class="form-control" rows="6" placeholder="评论内容" v-model="content"></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="button" class="btn btn-default pull-right" @click="getItem">提交</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
      props: {
          addComment :{
            type: Function,
            required: true
          }
      },
    data () {
        return {
          username:'',
          content:''
        }
    },
    methods: {
      getItem () {
        // 检查用户是否正常输入
        const {username , content} = this;
         if(!username.trim() || !content.trim()){
              alert('请正确输入内容');
           return;
         }
         //将获取到的内容保存为新对象
         const comment = {username , content}

         // 调用函数添加数据
        this.addComment(comment)

        // 清除输入框
         this.username = "";
         this.content = ""

      }
    }
  }
</script>

<style>

</style>
