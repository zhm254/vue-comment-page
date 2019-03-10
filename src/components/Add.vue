<template>
  <div>
    <div>请输入姓名：</div>
    <br/>
    <input v-model="name"/><br/><br/>
    <div>请输入评论内容：</div>
    <br/>
    <textarea v-model="content" rows="10" cols="40"></textarea><br/><br/>
    <button v-on:click="addItem">添加</button>
  </div>
</template>

<script>
  export default {
    name: 'Add',
    props: {
      comments: Array,
      addComment: Function
    },
    data: function () {
      return {
        name: '',
        content: ''
      }
    },
    methods: {
      addItem: function () {
        if (!this.name || !this.content) {
          alert('姓名和评论内容都不能为空。')
          return;
        }
        var name = this.name.trim();
        var content = this.content.trim();
        var comment = {
          name: name,
          content: content
        }
        this.addComment(comment);
        this.name = '';
        this.content = '';
      }
    }
  }
</script>


<style scoped lang="less">

</style>
