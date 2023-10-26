<template>
  <div class="home">
    <div class="home__banner">
      <h1 class="home__banner-title">Let Your Home Be Unique</h1>
      <p class="home__banner-text">There are many variations of the passages of lorem Ipsum fromavailable, majority.</p>
      <a href="#" class="home__banner-button">
        <p class="home__banner-button-text">Get Started</p>
        <svg xmlns="http://www.w3.org/2000/svg" width="18" height="17" viewBox="0 0 18 17" fill="none">
          <path d="M1 8.43542L14.7232 8.29857M9.61818 1.91138L16.1412 8.43436L9.48677 15.0887" stroke="#CDA274"
            stroke-width="2" stroke-linecap="square" stroke-linejoin="round" />
        </svg>
      </a>
    </div>
    <div class="home__projects">
      <h1 class="home__projects-title">Follow Our Projects</h1>
      <p class="home__projects-text">
        It is a long established fact that a reader will be distracted by the of readable content of page lookings at its
        layouts points.
      </p>
      <div class="home__projects-container">
        <ProjectCard v-for="(p, i) in projects" :key="i" :image="p.image" :title="p.title" :text="p.text"
          :position="p.position" />
      </div>
    </div>
    <div class="home__advantages-bg">
      <div class="home__advantages">
        <OurAdvantage v-for="(adv, i) in advantages" :key="i" :num="adv.num" :text="adv.text" :line="adv.line" />
      </div>
    </div>
    <div class="home__news">
      <h1 class="home__news-title">Articles & News</h1>
      <p class="home__news-text">
        It is a long established fact that a reader will be distracted by the of readable content of a page when lookings
        at its layouts the points of using.
      </p>
      <div class="home__news-container">
        <ArticlesNews v-for="(n, i) in news" :key="i" :image="n.image" :title="n.title" :date="n.date">
          {{ n.text }}
        </ArticlesNews>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import ProjectCard from '@/components/ProjectCard.vue'
import OurAdvantage from '@/components/OurAdvantage.vue'
import ArticlesNews from '@/components/ArticlesNews.vue'

export default {
  name: 'HomeView',
  components: {
    ProjectCard,
    OurAdvantage,
    ArticlesNews
  },
  data() {
    return {
      projects: [
        {
          image: require("../assets/photo1.png"),
          title: "Modern Kitchan",
          text: "Decor / Artchitecture",
          position: "top-left"
        },
        {
          image: require("../assets/photo2.png"),
          title: "Modern Kitchan",
          text: "Decor / Artchitecture",
          position: "top-right"
        },
        {
          image: require("../assets/photo3.png"),
          title: "Modern Kitchan",
          text: "Decor / Artchitecture",
          position: "bottom-left"
        },
        {
          image: require("../assets/photo4.png"),
          title: "Modern Kitchan",
          text: "Decor / Artchitecture",
          position: "bottom-right"
        }
      ],
      advantages: [
        {
          num: 12,
          text: "Years Of Experiance",
          line: true
        },
        {
          num: 85,
          text: "Success Project",
          line: true
        },
        {
          num: 15,
          text: "Active Project",
          line: true
        },
        {
          num: 95,
          text: "Happy CUstomers",
          line: false
        }
      ],
      news: [
        {
          image: require("../assets/photo5.png"),
          title: "Kitchan Design",
          date: "26 December,2022",
          text: "Let’s Get Solution For Building Construction Work"
        },
        {
          image: require("../assets/photo6.png"),
          title: "Living Design",
          date: "22 December,2022",
          text: "Low Cost Latest Invented Interior Designing Ideas."
        },
        {
          image: require("../assets/photo7.png"),
          title: "Interior Design",
          date: "25 December,2022",
          text: "Best For Any Office & Business Interior Solution"
        }
      ]
    };
  },
}
</script>

<style lang="scss">
.home {
  padding-top: 12px;
  padding-bottom: 96px;

  &__banner {
    @include content-wrapper;
    height: 758px;
    background-image: url(../assets/photo.png);
    background-color: lightgray;
    background-size: cover;
    background-repeat: no-repeat;
    // background: url(../assets/photo.png), lightgray / cover no-repeat;
    border-radius: 80px;
    // padding: 208px 0 208px 52px;
    padding-left: 52px;
    margin-bottom: 96px;
    display: flex;
    flex-direction: column;
    justify-content: center;

    &-title {
      @include font-dm(#292F36, 65px, 81.25px);
      max-width: 434px;
      margin-bottom: 18px;
    }

    &-text {
      @include font-jost(#4D5053, 22px, 33px, 0.22px);
      max-width: 434px;
      margin-bottom: 21px;
    }

    &-button {
      width: 223px;
      border-radius: 18px;
      background: #292F36;
      box-shadow: 0px 10px 20px 0px rgba(192, 192, 192, 0.35);
      padding: 26px 49px 26px 48px;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10px;

      &-text {
        @include font-jost(#FFF, 18px, 22.5px, 0.36px, 600);
      }
    }
  }

  &__projects {
    @include content-wrapper;
    margin-bottom: 96px;
    display: flex;
    flex-direction: column;
    align-items: center;

    &-title {
      @include font-dm(#292F36, 50px, 62.5px, 1px);
      margin-bottom: 8px;
    }

    &-text {
      @include font-jost(#4D5053, 22px, 33px, 0.22px);
      max-width: 737px;
      text-align: center;
      margin-bottom: 93px;
    }

    &-container {
      width: 100%;
      display: grid;
      grid-template-columns: 1fr 1fr;
      // grid-template-rows: auto;
      column-gap: 104px;
      row-gap: 56px;
    }
  }

  &__advantages-bg {
    background-color: #F4F0EC;
    padding-top: 151px;
    padding-bottom: 151px;
    margin-bottom: 96px;
  }

  &__advantages {
    @include content-wrapper;
    display: flex;
    justify-content: center;
  }

  &__news {
    @include content-wrapper;
    display: flex;
    flex-direction: column;
    align-items: center;

    &-title {
      @include font-dm(#292F36, 50px, 62.5px, 1px);
      margin-bottom: 12px;
    }

    &-text {
      @include font-jost(#4D5053, 22px, 33px, 0.22px);
      max-width: 811px;
      text-align: center;
      margin-bottom: 52px;
    }

    &-container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      column-gap: 27px;
    }
  }
}
</style>
