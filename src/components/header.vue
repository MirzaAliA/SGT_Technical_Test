<script>
export default {
    name: 'Header',
}

</script>

<template>
    <div class="header-container">
        <div class="header-wrapper">
            <div class="header-top">
                <img class="kucing-header kucing-header-1" src="../assets/images/kucing-header-1.svg" alt="">

                <h1 class="header-title">Innovative Solutions for Animals</h1>
            </div>
            <div class="header-bottom">
                <h3 class="header-description">charity organization</h3>
                <div class="header-logo">
                    <img class="logo" src="../assets/images/youtube.svg" alt="youtube">
                    <img class="logo" src="../assets/images/instagram.svg" alt="instagram">
                    <img class="logo" src="../assets/images/facebook.svg" alt="facebook">
                    <img class="logo" src="../assets/images/patreon.svg" alt="patreon">
                    <img class="logo" src="../assets/images/telegram.svg" alt="telegram">
                </div>
            </div>
        </div>
        <div class="arrow-down">
            <img src="" alt="">
        </div>
    </div>
</template>

<style>
.header-wrapper {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.header-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: var(--primaryAccsent);
    color: black;
    height: 100vh;
}

img.kucing-header {
    width: 15vw;
    height: 15vw;
}

h1.header-title {
    font-size: 4vw;
    width: 17vw;
}

h3.header-description {
    font-size: 2.5vw;
    font-weight: 500;
    letter-spacing: 1px;
}

.header-top {
    display: flex;
    flex-direction: row;
    gap: 4vw;
    justify-content: center;
    align-items: center;
}

.header-bottom {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1vw;
}

.header-logo {
    display: flex;
    gap: 1.5vw;
}

.header-logo img {
    width: 3vw;
}

.logo {
    transition: ease 0.3s;
}

.logo:hover {
    transform: scale(80%);
    transition: ease 0.3s;
}

@media only screen and (max-width: 900px) {

    .header-wrapper {
        gap: 2.5vw;
    }

    img.kucing-header {
        width: auto;
        height: 18vw;
    }

    h1.header-title {
        font-size: 5vw;
        width: 30vw;
        line-height: 5vw;
    }

    h3.header-description {
        margin-top: 2vw;
        font-size: 2.5vw;
    }

    .header-bottom {
        gap: 2vw;
    }


    .header-logo {
        gap: 2.5vw;
    }

    .header-logo img {
        width: 4.5vw;
    }

}

@media only screen and (max-width: 480px) {

    img.kucing-header {
        width: auto;
        height: 20vw;
    }

    h1.header-title {
        font-size: 6vw;
        width: 30vw;
        line-height: 6vw;
    }

    h3.header-description {
        margin-top: 2vw;
        font-size: 3.5vw;
    }

    .header-bottom {
        gap: 10vw;
    }

    .header-logo {
        gap: 2.5vw;
    }

    .header-logo img {
        width: 8vw;
    }

}
</style>
