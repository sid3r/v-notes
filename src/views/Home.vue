<template>
  <div class="home-wrapper">
    <div class="folders">
      folders
    </div>
    <div class="notes-list">
      list
    </div>
    <div class="note-view">
      view
    </div>
    <!-- new- button -->
    <a href="/" class="new-btn"
      ><img src="@/assets/plus.svg" alt="new note"
    /></a>
  </div>
</template>

<script>
export default {
  name: "Home"
};
</script>

<style lang="scss" scoped>
@import "../styles/variables";
.home-wrapper {
  display: flex;
  .folders,
  .notes-list,
  .note-view {
    height: calc(100vh - 50px);
    overflow-y: scroll;
    padding: 20px;
  }
  .folders {
    border-right: 1px solid #2a2b31;
    width: 200px;
  }
  .notes-list {
    border-right: 1px solid #2a2b31;
    width: 260px;
  }
  .note-view {
    flex: 1;
  }
  .new-btn {
    background: $primary;
    width: 42px;
    height: 42px;
    position: fixed;
    right: 20px;
    bottom: 20px;
    border-radius: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all ease-in-out 0.3s;
    &:hover {
      transform: scale(1.3);
    }
    img {
      width: 21px;
    }
  }
}
</style>
