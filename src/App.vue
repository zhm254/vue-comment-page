<template>
  <div>
    <h2>请添加评论</h2>
    <div class="add-list">
      <Add :comments="comments" :addComment="addComment" class="add"></Add>
      <List :comments="comments" :deleteComment="deleteComment"></List>
    </div>
  </div>
</template>

<script>
  import Add from './components/Add.vue'
  import List from './components/List.vue'

  export default {
    name: 'App',
    components: {
      Add,
      List
    },
    data: function () {
      return {
        comments: [
          {name: '小明', content: 'vue很好用。'},
          {name: '小华', content: 'vue挺好的。'},
          {name: '小刚', content: 'vue真好。'}
        ]
      }
    },
    methods: {
      addComment: function (comment) {
        this.comments.push(comment);
      },
      deleteComment: function (index) {
        this.comments.splice(index, 1);
      }
    }
  }
</script>

<style lang="less">
  h2 {
    text-align: center;
  }

  .add-list {
    display: flex;
    justify-content: flex-start;
  }

  .add {
    margin: 0 200px;
  }
</style>
