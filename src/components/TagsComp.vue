<template>
    <div class="tags">
        <h1 class="tags__title">Tags</h1>
        <div class="tags__tag-conteiner">
            <div v-for="(tag, i) in tags"
                 :key="i"
                 @click="selectTag(i)"
                 class="tags__tag"
                 :class="{ tags__tag_selected: isSelected[i] }">
                {{ tag }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        tags: Array
    },
    emits: [
        'selectTag'
    ],
    data() {
        return {
            isSelected: new Array(this.tags.length).fill(false)
        };
    },
    methods: {
        selectTag(index) {
            this.isSelected = this.isSelected.map((e, i) => i === index ? true : false);
            this.$emit('selectTag', this.tags[index]);
        }
    },
    mounted() {
        this.selectTag(0);
    },
}
</script>

<style lang="scss">
.tags {
    width: 100%;

    &__title {
        @include font-dm(#292F36, 25px, 31.25px, 0.5px);
        margin-bottom: 24px;
    }

    &__tag-conteiner {
        display: flex;
        flex-wrap: wrap;
        gap: 11px 10px;
    }

    &__tag {
        @include font-jost(#292F36, 18px, 22.5px, 0.36px);
        padding: 9px 30px;
        border-radius: 10px;
        background: #F4F0EC;

        &_selected {
            background: #292F36;
            color: #FFF;
        }
    }
}
</style>