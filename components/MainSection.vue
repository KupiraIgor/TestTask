<script setup lang="ts">
const onScrollToSingUp = () => {
  const el = document.querySelector('#post-section');
  if (el) {
    window.scrollTo({
      top: el.getBoundingClientRect().top + window.scrollY,
      behavior: 'smooth',
    });
  }
};
</script>

<template>
  <section class="main-section">
    <div class="container">
      <div class="main-section__body">
        <NuxtImg quality="80" format="webp" class="main-section__img" src="./first-section-bg.jpg" alt="bg-img" />
        <div class="main-section__content">
          <h1 class="main-section__title title">Test assignment for front-end developer</h1>
          <p class="main-section__subtitle">
            What defines a good front-end developer is one that has skilled knowledge of HTML, CSS, JS with a vast
            understanding of User design thinking as they'll be building web interfaces with accessibility in mind. They
            should also be excited to learn, as the world of Front-End Development keeps evolving.
          </p>
          <BaseButton @click="onScrollToSingUp">Sign up</BaseButton>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.main-section {
  padding-bottom: 7rem;

  &__body {
    position: relative;
    min-height: 65rem;
    display: flex;
    justify-content: center;
    align-items: center;

    &::after {
      content: '';
      position: absolute;
      z-index: 1;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
    }
  }

  &__img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  &__content {
    position: relative;
    z-index: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    max-width: 38rem;
  }

  &__title {
    color: var(--color-white);
    margin-bottom: 2rem;
  }

  &__subtitle {
    color: var(--color-white);
    text-align: center;
    margin-bottom: 3rem;
  }

  @media (max-width: 1100px) {
    .container {
      padding: 0 !important;
    }
  }

  @media (max-width: 1024px) {
    &__body {
      min-height: 50rem;
      padding: 0 1.6rem;
    }
  }
}
</style>
