<template>
    <div>

    </div>
</template>

<script>
export default {
    props: {
        size: Number,
        pageNum: Number,
        pageTotal: Number
    },
    data() {
        return {
            pagSize: Math.min(this.size, this.pageTotal),
            pageFrameCur: 0,
            pagFrame: null,
            pageNumFirst: this.pageNum
        };
    },
    methods: {
        selectPage(pagFrameIndex) {
            let index = pagFrameIndex >= 0 ? pagFrameIndex : 0;
            if(index >= this.pagSize - 1) {
                index = this.pagSize - 1
                let first = this.pageNumFirst + index;
                if(first + this.pagSize - 1 > this.pageTotal) {
                    const newfirst = this.pageTotal - this.pagSize + 1;
                    index = first - newfirst;
                    first = newfirst;
                } else {
                    index = 0;
                }
                this.pageNumFirst = first;
            }
            this.pageFrameCur = index;
            this.setPagFrame();
        },
        setPagFrame() {
            let frame = new Array(this.pagSize);
            for(let i = 0; i < frame.length; i++) {
                const selected = (i == this.pageFrameCur);
                const page = this.pageNumFirst + i;
                frame[i] = { pageNum: page, isSelected: selected };
            }
            this.pagFrame = frame;
        },
        nextPage() {
            this.selectPage(this.pageFrameCur + 1);
        },
        pageNumCur() {
            return this.pagFrame.find(x => x.isSelected).pageNum;
        }
    },
    mounted() {
        this.setPagFrame();
    },
}
</script>

<style lang="scss">
.pagination {
    display: flex;
    gap: 20px;

    &__num {}

    &__next {}
}
</style>