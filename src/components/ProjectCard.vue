<template>
    <div class="project-card">
        <div class="project-card__img" :class="'project-card__img_' + position">
            <!-- <img :src="image" alt="project"> -->
        </div>
        <div class="project-card__info">
            <div class="project-card__info-title-text">
                <h1 class="project-card__info-title">{{ title }}</h1>
                <p class="project-card__info-text">{{ text }}</p>
            </div>
            <div class="project-card__info-button">
                <svg xmlns="http://www.w3.org/2000/svg" width="70" height="70" viewBox="0 0 70 70" fill="none">
                    <circle cx="35" cy="35" r="35" fill="#F4F0EC" />
                    <path d="M32 44L40 35L32 26" stroke="#292F36" stroke-width="2" stroke-linecap="round"
                        stroke-linejoin="round" />
                </svg>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        image: String,
        title: String,
        text: String,
        // isTopLeft: Boolean,
        // isTopRight: Boolean,
        // isBottomRight: Boolean,
        // isBottomLeft: Boolean
        position: String
    }
}
</script>

<style scoped lang="scss">
.project-card {
    // width: 548px;
    display: flex;
    flex-direction: column;
    gap: 25px;

    &__img {
        width: 100%;
        height: 525px;
        background-image: v-bind("`url(${image})`");
        background-color: lightgray;
        background-size: cover;
        background-repeat: no-repeat;

        &_top-left {
            border-top-right-radius: 80px;
        }

        &_top-right {
            border-top-left-radius: 80px;
        }

        &_bottom-right {
            border-bottom-left-radius: 80px;
        }

        &_bottom-left {
            border-bottom-right-radius: 80px;
        }
    }

    &__info {
        display: flex;
        justify-content: space-between;

        &-title-text {
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            gap: 4px;
        }

        &-title {
            @include font-dm(#292F36, 25px, 31.25px, 0.5px);
        }

        &-text {
            @include font-jost(#4D5053, 22px, 33px, 0.22px);
        }

        &-button {
            width: 70px;
            height: 70px;
        }
    }
}
</style>