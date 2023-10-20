<template>
  <div class="blog">
    <div class="blog__banner">
      <div class="blog__banner-intro">
        <h1 class="blog__banner-intro-title">
          Articles & News
        </h1>
        <p class="blog__banner-intro-text">
          Home / Blog
        </p>
      </div>
    </div>
    <div class="blog__latest">
      <h1 class="blog__latest-title">Latest Post</h1>
      <LatestPost :img="latest.img" :title="latest.title" :texts="latest.texts" :date="latest.date"></LatestPost>
    </div>
    <div class="blog__news">
      <h1 class="blog__news-title">Articles & News</h1>
      <div class="blog__news-container">
        <ArticlesNews v-for="(n, i) in news" :key="i" :image="n.image" :title="n.title" :date="n.date">
          {{ n.text }}
        </ArticlesNews>
      </div>
      <div class="blog__news-pagination">
        <Pagination></Pagination>
      </div>
    </div>
  </div>
</template>

<script>
import ArticlesNews from '@/components/ArticlesNews.vue'
import Pagination from '@/components/Pagination.vue';
import LatestPost from '@/components/LatestPost.vue'

export default {
  name: 'BlogView',
  components: {
    LatestPost,
    ArticlesNews,
    Pagination
  },
  data() {
    return {
      latest: {
        img: require("../assets/blog_latest.png"),
        title: "Low Cost Latest Invented Interior Designing Ideas",
        texts: [
          "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief.",
          "Lorem Ipsum is not simply random text. It has roots in a piece of classica."
        ],
        date: "26 December,2022 "
      },
      news: [
        {
          image: require("../assets/blog_news1.png"),
          title: "Kitchan Design",
          date: "26 December,2022",
          text: "Let’s Get Solution For Building Construction Work"
        },
        {
          image: require("../assets/blog_news2.png"),
          title: "Living Design",
          date: "22 December,2022",
          text: "Low Cost Latest Invented Interior Designing Ideas."
        },
        {
          image: require("../assets/blog_news3.png"),
          title: "Interior Design",
          date: "25 December,2022",
          text: "Best For Any Office & Business Interior Solution"
        },
        {
          image: require("../assets/blog_news4.png"),
          title: "Kitchan Design",
          date: "26 December,2022",
          text: "Let’s Get Solution For Building Construction Work"
        },
        {
          image: require("../assets/blog_news5.png"),
          title: "Living Design",
          date: "22 December,2022",
          text: "Low Cost Latest Invented Interior Designing Ideas."
        },
        {
          image: require("../assets/blog_news6.png"),
          title: "Interior Design",
          date: "25 December,2022",
          text: "Best For Any Office & Business Interior Solution"
        }
      ]
    }
  },
}
</script>

<style lang="scss">
.blog {
  &__banner {
    width: 100%;
    height: 356px;
    background-image: url(../assets/blog_banner.png);
    background-color: lightgray;
    background-size: cover;
    background-repeat: no-repeat;
    margin-bottom: 200px;
    display: flex;
    justify-content: center;
    align-items: end;

    &-intro {
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

  &__latest {
    @include content-wrapper;
    margin-bottom: 150px;

    &-title {
      @include font-dm(#292F36, 50px, 62.5px, 1px);
      margin-bottom: 27px;
    }
  }

  &__news {
    @include content-wrapper;
    margin-bottom: 200px;

    &-title {
      @include font-dm(#292F36, 50px, 62.5px, 1px);
      margin-bottom: 30px;
    }

    &-container {
      margin-bottom: 51px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      column-gap: 27px;
      row-gap: 30px;
    }

    &-pagination {
      display: flex;
      justify-content: center;
    }
  }
}
</style>