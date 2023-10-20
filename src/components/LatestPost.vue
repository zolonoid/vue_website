<template>
    <div class="latest-post">
        <div class="latest-post__img"></div>
        <div class="latest-post__desc-info">
            <h1 class="latest-post__desc-info-title">
                {{ title }}
            </h1>
            <div class="latest-post__desc">
                <p v-for="text in texts" class="latest-post__desc-text">
                    {{ text }}
                </p>
            </div>
            <div class="latest-post__info">
                <p class="latest-post__info-date">{{ date }}</p>
                <div class="latest-post__info-button">
                    <svg xmlns="http://www.w3.org/2000/svg" width="52" height="53" viewBox="0 0 52 53" fill="none">
                        <circle cx="26" cy="26.5" r="26" fill="#F4F0EC" />
                        <path d="M23.771 33.1855L29.7139 26.4998L23.771 19.8141" stroke="#292F36" stroke-width="2"
                            stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        img: String,
        title: String,
        texts: Array,
        date: String
    }
}
</script>

<style lang="scss">
.latest-post {
    width: 100%;
    border-radius: 62px;
    border: 1px solid #E7E7E7;
    box-shadow: 0px 10px 30px 0px rgba(255, 255, 255, 0.25);
    padding: 22px;
    margin-bottom: 150px;
    display: flex;
    align-items: center;
    gap: 65px;

    &__img {
        width: 569px;
        height: 478px;
        background-image: v-bind("`url(${img})`");
        background-color: lightgray;
        background-size: cover;
        background-repeat: no-repeat;
        border-radius: 50px;
    }

    &__desc-info {
        width: 489px;

        &-title {
            @include font-dm(#292F36, 25px, 31.25px, 0.5px);
            max-width: 463px;
            margin-bottom: 22px;
        }
    }

    &__desc {
        margin-bottom: 41px;
        display: flex;
        flex-direction: column;
        gap: 45px;

        &-text {
            @include font-jost(#4D5053, 22px, 33px, 0.22px);
            max-width: 469px;
        }
    }

    &__info {
        display: flex;
        justify-content: space-between;
        align-items: center;

        &-date {
            @include font-jost(#4D5053, 16px, 24px, 0.16px);
            text-transform: capitalize;
        }

        &-button {
            width: 52px;
            height: 52px;
        }
    }
}
</style>