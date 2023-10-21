<template>
    <div class="pagination">
        <div v-for="(p, i) in pagFrame"
             @click="selectPage(i)"
             class="pagination__num"
             :class="{ pagination__num_selected: p.isSelected }">
            {{ p.pageNum }}
        </div>
        <div class="pagination__next" @click="nextPage">
            <svg xmlns="http://www.w3.org/2000/svg" width="53" height="52" viewBox="0 0 53 52" fill="none">
                <circle cx="26.5" cy="26" r="25.5" stroke="#CDA274" />
                <path d="M23.5571 32L29.5 25.3143L23.5571 18.6286" stroke="#292F36" stroke-width="2" stroke-linecap="round"
                      stroke-linejoin="round" />
            </svg>
        </div>
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

    &__num {
        width: 52px;
        height: 52px;
        background-size: cover;
        background-repeat: no-repeat;
        background-image: url(../assets/pag.png);
        display: flex;
        justify-content: center;
        align-items: center;

        &_selected {
            background-image: url(../assets/curpag.png);
        }
    }

    &__next {
        width: 52px;
        height: 52px;
    }
}
</style>