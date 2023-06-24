<template>
  <div class="header">
    <h3>Header</h3>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
  }
}
</script>


<style scoped>

  .header{
    width: 100%;
    height: 50px;
    background-color: rgb(10, 25, 17);
    display: flex;
    align-items: center;
    position: fixed;
    z-index: 1;
    box-shadow: 1px 1px 4px rgb(11, 45, 27);
  }

  .header h3{
    color: white;
    margin-left: 10px;
  }

</style>
