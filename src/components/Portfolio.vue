<template>
    <section class="portfolio" id="portfolio">
        <h1 class="portfolio-title">
            Portfólio
        </h1>
        <Slider />
    </section>
</template>

<script>
import Slider from './Slider.vue'
export default {
  components: { Slider },
    setup(){

    }
}
</script>

<style lang="scss" scoped>
    .portfolio {
        margin: 120px 0;
    }
    .portfolio-title {
        max-width: 960px;
        margin: 32px auto;
        padding: 12px 0;

        text-align: center;

        font-size: 50px;
        font-weight: 700;
        color: #d9d9d9;
        letter-spacing: 1.5px;
    }
</style>
