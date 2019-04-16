<template>
  <div class="g-button-group">
    <slot></slot>
  </div>
</template>

<script>
export default{
  mounted() {
    console.log("here");
    for(let node of this.$el.children){
      let name = node.nodeName.toLowerCase()
      if(name !== 'button'){
        console.warn(`g-button-group 的子元素应该是 button,而你的是${name}`);
      }
    }
  }
}
</script>

<style lang="scss">
  .g-button-group{
    display:flex;
    margin-top: 100px;
    > .g-button{
      border-radius: 0;
      margin-left: -1px;
      &:first-child{
        border-top-left-radius: var(--button-radius);
        border-bottom-left-radius: var(--button-radius);
      }
      &:last-child{
        border-top-right-radius: var(--button-radius);
        border-bottom-right-radius: var(--button-radius);
      }
      &:hover{
        position: relative;
        z-index: 1;
      }
    }
  }
</style>