<template>
    <div class="project-details">
        <div class="project-details__banner">
            <BannerComp :image="require('../assets/project_details_banner.png')"></BannerComp>
        </div>
        <div class="project-details__info">
            <h1 class="project-details__info-title">
                {{ title }}
            </h1>
            <p v-for="(text, i) in texts" :key="i" class="project-details__info-text">
                {{ text }}
            </p>
        </div>
        <div class="project-details__slider">
            <SliderComp :images="images"></SliderComp>
        </div>
    </div>
</template>

<script>
import { mapState } from "vuex";
import BannerComp from '@/components/BannerComp.vue';
import SliderComp from '@/components/SliderComp.vue';

export default {
    components: {
        BannerComp,
        SliderComp
    },
    computed: {
        ...mapState(["title", "texts", "images"])
    }
}
</script>

<style lang="scss">
.project-details {
    margin-bottom: 200px;
    &__banner {
        margin-bottom: 200px;
    }

    &__info {
        @include content-wrapper;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-bottom: 45px;

        &-title {
            @include font-dm(#292F36, 50px, 62.5px, 1px);
            margin-bottom: 11px
        }

        &-text {
            @include font-jost(#4D5053, 22px, 33px, 0.22px);
            width: 658px;
            margin-bottom: 55px;
        }
    }

    &__slider{
        @include content-wrapper;
    }
}
</style>

