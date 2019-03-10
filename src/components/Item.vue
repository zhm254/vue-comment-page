<template>
  <li>
    <div>{{comment.name}}说：</div>
    <br/>
    <div>{{comment.content}}</div>
    <br/>
    <button @click="deleteItem">删除</button>
    <br/>
    <br/>
  </li>
</template>
<script>
  export default {
    name: 'Item',
    props: ['comment', 'index', 'deleteComment'],
    methods: {
      deleteItem: function () {
        if (window.confirm(`确定删除${this.comment.name}的评论吗？`)) {
          this.deleteComment(this.index);
        }
      }
    }
  }
</script>
<style>

</style>
