<template>
  <div>
    <ul>
      <Item v-for="(comment,index) in comments" :key="index" :comment="comment" :index="index"
            :deleteComment="deleteComment"></Item>
    </ul>
    <div v-if="this.comments.length===0">暂无评论。</div>
  </div>
</template>
<script>
  import Item from './Item.vue'

  export default {
    name: 'List',
    components: {
      Item
    },
    props: {
      comments: Array,
      deleteComment: Function
    },
  }
</script>
<style>

</style>
