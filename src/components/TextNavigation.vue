<template>
  <ul class="gnavi">
    <li class="current"><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Service</a></li>
  </ul>
</template>

<style scoped>
  .gnavi {
    display: flex;
    justify-content: center;
    margin: 0 0 50px 0;
    list-style: none;
  }
  .gnavi a {
    display: block;
    padding: 10px 30px;
    text-decoration: none;
    color: #333;
  }
  .gnavi li {
    margin-bottom: 20px;
  }
  .gnavi li a {
    /* 線の基点とするためrelativeを指定 */
    position: relative;
  }
  .gnavi li.current a,
  .gnavi li.a:hover {
    color: #0481a2;
  }
  .gnavi li a::after {
    content: '';
    /* 絶対位置で線の位置を決める */
    position: absolute;
    bottom: 0;
    left: 10%;
    /* 線の形状 */
    width: 80%;
    height: 2px;
    background: #0481a2;
    /* アニメーションの指定 */
    transition: all 0.3s;
    transform: scale(0, 1); /* X方向0，Y方向1 */
    /* 上部中央基点 */
    transform-origin: center top;
  }
  /* 現在地とhoverの設定 */
  .gnavi li.current a::after,
  .gnavi li a:hover::after {
    /* x方向にスケール拡大 */
    transform: scale(1, 1);
  }
</style>
