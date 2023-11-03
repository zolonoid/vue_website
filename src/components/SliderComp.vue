<template>
    <div class="slider">
        <div class="slider__img"></div>
        <div class="slider__pngwing">
            <div v-for="(img, i) in imgs" :key="i"
                 class="slider__pngwing-item"
                 :class="{ 'slider__pngwing-item_selected': img.selected }"
                 @click="selectImage(i)">
                <svg width="26" height="26" xmlns="http://www.w3.org/2000/svg">
                    <g>
                        <title>background</title>
                        <rect fill="#fff" id="canvas_background" height="20" width="20" y="-1" x="-1" />
                        <g display="none" overflow="visible" y="0" x="0" height="100%" width="100%" id="canvasGrid">
                            <rect fill="url(#gridpattern)" stroke-width="0" y="0" x="0" height="100%" width="100%" />
                        </g>
                    </g>
                    <g>
                        <title>Layer 1</title>
                        <ellipse ry="10" rx="10" id="svg_1" cy="12" cx="12" stroke-width="2.5" stroke="#000" fill="#fff" />
                    </g>
                </svg>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        images: Array
    },
    data() {
        return {
            imgs: this.images.map((v, i) => {
                return { img: v, selected: i === 0 };
            })
        };
    },
    methods: {
        selectImage(index) {
            this.imgs = this.imgs.map((e, i) => {
                return { img: e.img, selected: i === index }
            });
        }
    },
}
</script>

<style lang="scss">
.slider {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;

    &__img {
        height: 799px;
        border-radius: 70px;
        background-image: v-bind("`url(${img})`");
        background-color: #C4C4C4;
        background-size: cover;
        background-repeat: no-repeat;
    }

    &__pngwing {
        display: flex;
        gap: 9px;

        &-item {
            width: 26px;
            height: 26px;

            &_selected {
                & svg ellipse {
                    fill: aqua;
                }
            }
        }
    }
}
</style>