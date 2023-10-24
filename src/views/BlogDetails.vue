<template>
    <div class="blog-details">
        <div class="blog-details__banner"></div>
        <div class="blog-details__wrapper">
            <div class="blog-details__content-container">
                <div v-for="(b, i) in blogsTag" :key="i" class="blog-details__content">
                    <h1 class="blog-details__content-title">
                        {{ b.title1 }}
                    </h1>
                    <div class="blog-details__content-img1" :style="{ backgroundImage: `url(${b.img1})` }"></div>
                    <div class="blog-details__content-date">
                        <p>26 December,2022</p>
                        <p>Interior / Home / Decore</p>
                    </div>
                    <p class="blog-details__content-text">
                        Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to
                        popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have
                        suffered alteration in some form, by injecthumour, or randomised words which don't look even
                        slightly believable.
                    </p>
                    <p class="blog-details__content-text">
                        Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to
                        repeat predefined chunks as necessary.
                    </p>
                    <div class="blog-details__content-quotes">
                        <h1 class="blog-details__content-quotes-title">“</h1>
                        <p class="blog-details__content-quotes-text">
                            The details are not the details. They make the design.
                        </p>
                    </div>
                    <h1 class="blog-details__content-title">
                        {{ b.title2 }}
                    </h1>
                    <p class="blog-details__content-text">
                        Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to
                        popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have
                        suffered.
                    </p>
                    <div class="blog-details__content-points">
                        <div v-for="n in 3" :key="n" class="blog-details__content-points-item">
                            <div class="blog-details__content-points-item-num">{{ n }}</div>
                            <p class="blog-details__content-text">
                                Contrary to popular belief.There are many variations of passages of Lorem Ipsum available,
                                but the majority have suffered.
                            </p>
                        </div>
                    </div>
                    <div class="blog-details__content-img2" :style="{ backgroundImage: `url(${b.img2})` }"></div>
                    <p class="blog-details__content-text">
                        Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to
                        popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have
                        suffered.
                    </p>
                </div>
            </div>
            <div class="blog-details__tags">
                <TagsComp
                          :tags="['Kitchen', 'Bedroom', 'Building', 'Architecture', 'Kitchen Planning', 'Bedroom']"
                          @selectTag="e => filterByTag(e)">
                </TagsComp>
            </div>
        </div>
    </div>
</template>

<script>
import TagsComp from '@/components/TagsComp.vue';

export default {
    components: {
        TagsComp
    },
    data() {
        return {
            blogs: [
                {
                    tag: "Kitchen",
                    title1: "Let’s Get Solution for Building Construction Work",
                    img1: require("../assets/blog_details1.png"),
                    title2: "Design sprints are great",
                    img2: require("../assets/blog_details1_1.png")
                },
                {
                    tag: "Bedroom",
                    title1: "Low Cost Latest Invented Interior Designing Ideas",
                    img1: require("../assets/blog_details5.png"),
                    title2: "Design sprints are great",
                    img2: require("../assets/blog_details7.png")
                },
                {
                    tag: "Building",
                    title1: "Best For Any Office & Business Interior Solution",
                    img1: require("../assets/blog_details6.png"),
                    title2: "Design sprints are great",
                    img2: require("../assets/blog_details3.png")
                },
                {
                    tag: "Architecture",
                    title1: "Let’s Get Solution for Building Construction Work",
                    img1: require("../assets/blog_details3.png"),
                    title2: "Design sprints are great",
                    img2: require("../assets/blog_details6.png")
                },
                {
                    tag: "Kitchen Planning",
                    title1: "Low Cost Latest Invented Interior Designing Ideas",
                    img1: require("../assets/blog_details2.png"),
                    title2: "Design sprints are great",
                    img2: require("../assets/blog_details4.png")
                },
                {
                    tag: "Bedroom",
                    title1: "Best For Any Office & Business Interior Solution",
                    img1: require("../assets/blog_details7.png"),
                    title2: "Design sprints are great",
                    img2: require("../assets/blog_details5.png")
                }
            ],
            blogsTag: []
        };
    },
    methods: {
        filterByTag(tag) {
            this.blogsTag = this.blogs.filter(x => x.tag === tag);
        }
    },
}
</script>

<style lang="scss">
.blog-details {
    margin-bottom: 96px;

    &__banner {
        width: 100%;
        height: 351px;
        background-image: url(../assets/blog_details_banner.png);
        background-size: cover;
        background-repeat: no-repeat;
        margin-bottom: 200px;
    }

    &__wrapper {
        @include content-wrapper;
        display: flex;
        justify-content: space-between;
    }

    &__content-container {
        display: flex;
        flex-direction: column;
        gap: 150px;
    }

    &__content {
        width: 799px;

        &-title {
            @include font-dm(#292F36, 50px, 62.5px, 1px);
            margin-bottom: 20px;
        }

        &-img1 {
            height: 539px;
            background-size: cover;
            background-repeat: no-repeat;
            margin-bottom: 46px;
        }

        &-date {
            @include font-jost(#4D5053, 16px, 24px, 0.16px);
            text-transform: capitalize;
            display: flex;
            gap: 409px;
            margin-bottom: 48px;
        }

        &-text {
            @include font-jost(#4D5053, 22px, 22px, 0.22px);
        }

        &-img2 {
            height: 365px;
            background-size: cover;
            background-repeat: no-repeat;
            margin-top: 44px;
            margin-bottom: 35px;
        }

        &-quotes {
            border-radius: 50px;
            background: #F4F0EC;
            padding-top: 53px;
            padding-bottom: 53px;
            margin-top: 35px;
            margin-bottom: 27px;
            display: flex;
            flex-direction: column;
            align-items: center;

            &-title {
                @include font-dm(#CDA274, 200px, 250px, 4px);
                font-style: italic;
            }

            &-text {
                @include font-dm(#CDA274, 25px, 31.25px, 0.5px);
                font-style: italic;
                text-align: center;
                max-width: 345px;
            }
        }

        &-points {
            width: 732px;
            display: flex;
            flex-direction: column;
            gap: 32px;

            &-item {
                display: flex;
                gap: 14px;

                &-num {
                    @include font-dm(#CDA274, 20px, 25px, 0.4px);
                }
            }
        }
    }

    &__tags {
        width: 345px;
    }
}
</style>