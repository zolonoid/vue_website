<template>
    <div class="project">
        <div class="project__banner">
            <BannerComp
                        :image="require('../assets/project_banner.png')"
                        title="Our Project"
                        text="Home / Project">
            </BannerComp>
        </div>
        <div class="project__categories">
            <CategoriesComp
                            :categories="['Bathroom', 'Bed Room', 'Kitchan', 'Living Area']"
                            :selectIndex="1"
                            @selectCategory="e => filterByCategory(e)">
            </CategoriesComp>
        </div>
        <div class="project__container">
            <div class="project__container-left">
                <ProjectCard v-for="(p, i) in projectsCategoryLeft" :key="i"
                             :image="p.image"
                             :title="p.title"
                             :text="p.text"
                             :isChosen="p.isChosen">
                </ProjectCard>
            </div>
            <div class="project__container-right">
                <ProjectCard v-for="(p, i) in projectsCategoryRight" :key="i"
                             :image="p.image"
                             :title="p.title"
                             :text="p.text"
                             :isChosen="p.isChosen">
                </ProjectCard>
            </div>
        </div>
        <div class="project__pagination">
            <PaginationComp :size="3" :pageNum="1" :pageTotal="10"></PaginationComp>
        </div>
    </div>
</template>

<script>
import BannerComp from '@/components/BannerComp.vue';
import CategoriesComp from '@/components/CategoriesComp.vue';
import ProjectCard from '@/components/ProjectCard.vue';
import PaginationComp from '@/components/PaginationComp.vue';

class Project {
    constructor(category, image, title, isChosen = false) {
        this.category = category;
        this.image = image;
        this.title = title;
        this.text = "Decor / Artchitecture";
        this.isChosen = isChosen;
    }
}

export default {
    components: {
        BannerComp,
        CategoriesComp,
        ProjectCard,
        PaginationComp
    },
    data() {
        return {
            projects: [
                new Project("Bed Room", require("../assets/project1.png"), "Minimal Bedroom", true),
                new Project("Bed Room", require("../assets/project2.png"), "Minimal Bedroom"),
                new Project("Bed Room", require("../assets/project3.png"), "Classic Minimal Bedroom"),
                new Project("Bed Room", require("../assets/project4.png"), "Modern Bedroom", true),
                new Project("Bed Room", require("../assets/project5.png"), "Minimal Bedroom table"),
                new Project("Bed Room", require("../assets/project6.png"), "System Table"),
                new Project("Bed Room", require("../assets/project7.png"), "Modern Medroom"),
                new Project("Bed Room", require("../assets/project8.png"), "Modern Bedroom"),
            ],
            projectsCategoryLeft: [],
            projectsCategoryRight: []
        };
    },
    methods: {
        filterByCategory(category) {
            let projectsCategory = this.projects.filter(x => x.category === category);
            this.projectsCategoryLeft = projectsCategory.filter((x, i) => i % 2 === 0);
            this.projectsCategoryRight = projectsCategory.filter((x, i) => i % 2 > 0);
        }
    }
}
</script>

<style lang="scss">
.project {
    padding-bottom: 200px;

    &__banner {
        width: 100%;
        margin-bottom: 200px;
    }

    &__categories {
        display: flex;
        justify-content: center;
        margin-bottom: 61px;
    }

    &__container {
        @include content-wrapper;
        display: flex;
        gap: 30px;
        margin-bottom: 61px;

        &-left {
            display: flex;
            flex-direction: column;
            gap: 35px;
        }

        &-right {
            display: flex;
            flex-direction: column;
            gap: 35px;
        }
    }

    &__pagination {
        display: flex;
        justify-content: center;
    }
}
</style>