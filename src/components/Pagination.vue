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
    data()
    {
        return {
            pagSize: Math.min(this.size, this.pageTotal),
            pageFrameCur: this.pageNum,
            pagFrame: new Array(pagSize)
        };
    },
    methods: {
        selectPage(pagFrameIndex)
        {
            let index = pagFrameIndex >= 0 ? pagFrameIndex : 0;
            if(index >= this.pagSize) index = this.pagSize - 1;
            this.pageFrameCur=index+1;
            //this.pagFrame=this.pagFrame.map((e,i)=>i==index?)
        },
        setPagFrame()
        {
            for(let i = 0; i < this.pagFrame.length; i++)
                this.pagFrame[i] = this.pageNumCur + i;
        }
    },
    mounted()
    {
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