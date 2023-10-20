<template>
    <div class="advantage" :class="{ advantage_line: line }">
        <h1 class="advantage__num">{{ num }}</h1>
        <p class="advantage__text">{{ text }}</p>
    </div>
</template>

<script>
export default {
    props: {
        num: Number,
        text: String,
        line: Boolean
    }
}
</script>

<style lang="scss">
.advantage {
    width: 300px;
    display: flex;
    flex-direction: column;
    justify-content: end;
    align-items: center;
    gap: 30px;

    &_line {
        border-right: 1px solid #CDA274;
    }

    &__num {
        @include font-dm(#CDA274, 85px, 106.25px, 1.7px);
    }

    &__text {
        @include font-jost(#4D5053, 22px, 33px, 0.22px);
    }
}
</style>