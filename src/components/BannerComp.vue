<template>
    <div class="banner">
        <div v-if="title && text" class="banner__intro">
            <h1 class="banner__intro-title">
                {{ title }}
            </h1>
            <p class="banner__intro-text">
                {{ text }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        image: String,
        title: {
            type: String,
            default: "",
            required: false
        },
        text: {
            type: String,
            default: "",
            required: false
        }
    }
}
</script>

<style scoped lang="scss">
.banner {
    width: 100%;
    height: 356px;
    background-image: v-bind('`url(${image})`');
    background-color: lightgray;
    background-size: cover;
    background-repeat: no-repeat;
    margin-bottom: 200px;
    display: flex;
    justify-content: center;
    align-items: end;

    &__intro {
        width: 503px;
        height: 178px;
        border-radius: 37px 37px 0px 0px;
        background: #FFF;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 10px;

        &-title {
            @include font-dm(#292F36, 50px, 62.5px);
        }

        &-text {
            @include font-jost(#4D5053, 22px, 33px, 0.22px);
        }
    }
}
</style>