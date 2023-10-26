<template>
    <div class="articles-news">
        <div class="articles-news__img">
            <div class="articles-news__img-title">{{ title }}</div>
        </div>
        <h1 class="articles-news__desc">
            <slot></slot>
        </h1>
        <div class="articles-news__info">
            <p class="articles-news__info-date">{{ date }}</p>
            <div class="articles-news__info-button">
                <svg xmlns="http://www.w3.org/2000/svg" width="52" height="53" viewBox="0 0 52 53" fill="none">
                    <circle cx="26" cy="26.267" r="26" fill="#F4F0EC" />
                    <path d="M23.7714 32.9527L29.7143 26.267L23.7714 19.5813" stroke="#292F36" stroke-width="2"
                        stroke-linecap="round" stroke-linejoin="round" />
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
        date: String
    },
    data() {
        return {
            img: this.$props.image
        }
    },
}
</script>

<style scoped lang="scss">
.articles-news {
    width: 383px;
    border-radius: 62px;
    border: 1px solid #E7E7E7;
    box-shadow: 0px 10px 30px 0px rgba(255, 255, 255, 0.25);
    padding: 21px 21px 38px 21px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    &:hover {
        background: #F4F0EC;

        & .articles-news__info-button svg circle {
            fill: #FFF;
        }
    }

    &__img {
        width: 340px;
        height: 290px;
        background-image: v-bind("`url(${img})`");
        background-color: lightgray;
        background-size: cover;
        background-repeat: no-repeat;
        // background: v-bind("`url(${img}), lightgray 50% / cover no-repeat`");
        border-radius: 45px 45px 0px 0px;
        padding-left: 20px;
        padding-bottom: 20px;
        margin-bottom: 21px;
        display: flex;
        // flex-direction: column;
        // justify-content: end;
        align-items: end;

        &-title {
            width: 124px;
            height: 41px;
            border-radius: 8px 8px 8px 0px;
            background: #FFF;
            padding-left: 11px;
            display: flex;
            align-items: center;
        }
    }

    &__desc {
        @include font-dm(#292F36, 25px, 31.25px, 0.5px);
        width: 305px;
        margin-bottom: 30px;
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