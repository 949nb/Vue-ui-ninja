<template>
  <div class="g-button-group">
    <slot></slot>
  </div>
</template>

<script>
export default{}
</script>

<style lang="scss">
  .g-button-group{
    display:flex;
    margin-top: 100px;
    > .g-button{
      border-radius: 0;
      &:first-child{
        border-top-left-radius: var(--button-radius);
        border-bottom-left-radius: var(--button-radius);
      }
      &:last-child{
        border-top-right-radius: var(--button-radius);
        border-bottom-right-radius: var(--button-radius);
      }
    }
  }
</style>