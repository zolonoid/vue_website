<template>
    <div class="error">
        <div class="error__info">
            <h1 class="error__info-title">404</h1>
            <p class="error__info-text">
                We are sorry, but the page
                you requested was not found
            </p>
            <router-link class="error__info-button" to="/">
                Back To Home
                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="17" viewBox="0 0 18 17" fill="none">
                    <path d="M1.85938 8.43542L15.5826 8.29857M10.4776 1.91138L17.0005 8.43436L10.3461 15.0887"
                          stroke="#CDA274" stroke-width="2" stroke-linecap="square" stroke-linejoin="round" />
                </svg>
            </router-link>
        </div>
        <img src="../assets/error.png" alt="error" class="error__img">
    </div>
</template>

<style lang="scss">
.error {
    padding-left: calc(50% - 600px);
    display: flex;
    align-items: center;
    gap: 81px;
    margin-bottom: 200px;

    &__info {
        &-title {
            @include font-dm(#CDA274, 250px, 215.5px);
            margin-bottom: 15px;
        }

        &-text {
            @include font-dm(#292F36, 35px, 52.5px, 0.35px);
            width: 569px;
            margin-bottom: 40px;
        }

        &-button {
            @include font-jost(#FFF, 18px, 22.5px, 0.36px, 600);
            border-radius: 18px;
            background: #292F36;
            box-shadow: 0px 10px 20px 0px rgba(192, 192, 192, 0.35);
            // padding: 26px 54px;
            width: 253px;
            height: 75px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }
    }

    &__img {
        width: 913px;
        height: 1042px;
        border-radius: 0px 0px 0px 353px;
        background: #EBEBEB;
    }
}
</style>