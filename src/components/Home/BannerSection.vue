<template>
  <div class="hero relative">
    <div class="bg-overlay" />
    <div class="title-wrap">
      <span class="title-line top font-prata">Hoàng</span>
      <span class="title-amp font-arcittya-begatri">&</span>
      <span class="title-line bottom font-prata">Phương</span>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
  .hero {
    height: min(80vh, 900px);
    min-height: 420px;
    position: relative;
    background-image: url('@/assets/images/banner.jpeg');
    background-size: cover;
    background-position: 60% 50%;
    background-repeat: no-repeat;
    content-visibility: auto; /* avoid rendering offscreen hero content */
    contain-intrinsic-size: 900px 600px; /* reserve size to prevent layout jank */
  }

  /* gradient dưới giúp chữ nổi bật hơn */
  .bg-overlay {
    position: absolute;
    inset: 0;
    pointer-events: none;
    background: linear-gradient(0deg, rgba(0, 0, 0, 0.55) 0%, rgba(0, 0, 0, 0) 55%);
  }

  /* Khối chữ: đặt ở góc trái dưới theo % để luôn tương đối */
  .title-wrap {
    position: absolute;
    left: 4%;
    bottom: 4%;
    color: #fff;
    text-transform: uppercase;
    line-height: 0.88;
    display: grid;
    grid-auto-rows: max-content;
    align-items: end;
  }

  /* Cỡ chữ responsive:
   - min px  - cỡ nhỏ nhất khi màn hình nhỏ
   - preferred theo vw
   - max px  - giới hạn trên để không quá to
*/
  .title-line.top {
    font-size: clamp(70px, 6.5vw, 75px);
  }
  .title-amp {
    display: inline-block;
    font-size: clamp(100px, 6.5vw, 115px);
    line-height: 0.9;
    margin: clamp(-14px, -0.6vw, -12px) 0 clamp(-2px, -0.2vw, -4px) clamp(2px, 0.4vw, 8px);
    text-shadow:
      0 2px 6px rgba(0, 0, 0, 0.35),
      0 0 1px rgba(0, 0, 0, 0.25);
  }
  .title-line.bottom {
    font-size: clamp(70px, 6.5vw, 75px);
    /* đẩy nhẹ sang phải để tạo bố cục lệch như mẫu */
    transform: translateX(clamp(30px, 1.5vw, 50px));
  }

  /* Khoảng cách dọc giữa các hàng cũng responsive */
  .title-line.top {
    margin-bottom: clamp(2px, 0vw, 10px);
  }
  .title-amp {
    margin-bottom: clamp(0px, 0.2vw, 4px);
  }

  /* Breakpoints tinh chỉnh thêm khi màn hình rất lớn */
  @media (min-width: 1280px) {
    .title-wrap {
      left: 5%;
      bottom: 5%;
    }
    .title-line.bottom {
      transform: translateX(24px);
    }
  }
</style>
