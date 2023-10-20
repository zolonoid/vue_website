<template>
    <div class="header">
        <div class="header__logo"><img src="../assets/logo.png" alt=""></div>
        <nav class="header__menu">
            <router-link class="header__menu-link" to="/">Home</router-link>
            <router-link class="header__menu-link" to="/project">Project</router-link>
            <router-link class="header__menu-link" to="/blog">Blog</router-link>
        </nav>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
.header {
    @include content-wrapper;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 55px;

    &__logo {
        width: 177px;
        height: 50px;
    }

    &__menu {
        display: flex;
        gap: 50px;

        &-link {
            @include font-jost(#292F36, 20px, 25px);
            color: #292F36;
        }
    }
}
</style>