<template>
    <div class="categories">
        <div v-for="(category, i) in categories"
             :key="i"
             @click="selectCategory(i)"
             class="categories__item"
             :class="{ categories__item_selected: isSelected[i] }">
             {{ category }}
        </div>
    </div>
</template>

<script>
export default {
    props: {
        categories: Array,
        selectIndex: Number
    },
    emits: [
        'selectCategory'
    ],
    data() {
        return {
            isSelected: new Array(this.categories.length).fill(false)
        };
    },
    methods: {
        selectCategory(index) {
            this.isSelected = this.isSelected.map((e, i) => i === index ? true : false);
            this.$emit('selectCategory', this.categories[index]);
        }
    },
    mounted() {
        this.selectCategory(this.selectIndex);
    },
}
</script>

<style lang="scss">
.categories {
    border-radius: 18px;
    border: 1px solid #CDA274;
    display: flex;
    justify-content: center;
    gap: 96px;

    &__item {
        @include font-jost(#292F36, 18px, 22.5px, 0.36px, 600);
        border-radius: 18px;
        padding: 26px 66px;

        &_selected {
            color: #FFF;
            background-color: #CDA274;
        }
    }
}
</style>