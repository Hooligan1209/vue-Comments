<template>

    <div>
      <header class="site-header jumbotron">
        <div class="container">
          <div class="row">
            <div class="col-xs-12">
              <h1>请发表对Vue的评论</h1>
            </div>
          </div>
        </div>
      </header>
      <div class="container">
        <add :add-comment="addComment"></add>
        <list :comments="comments" :delete-item="deleteItem"></list>
      </div>
    </div>

</template>

<script>
  import add from './components/add.vue'
  import list from './components/comments-list.vue'
  export default {
    data () {
        return {
          comments: []
        }
    },
    created(){
        const comments = [
          {username:'Tom' , content:'举头望明月'},
          {username:'Ros' , content:'低头思故乡'}
        ];
        setTimeout(() => {
            this.comments = comments
        } , 2000)
    },
    methods: {
      addComment(comment){
          this.comments.unshift(comment)
      },
      deleteItem(index){
          this.comments.splice(index , 1)
      }
    },
    // 将组件标签转换为元素标签
    components: {
      add,
      list
    }
  }
</script>

<style>

</style>
