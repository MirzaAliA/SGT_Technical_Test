<script>
import { gsap } from 'gsap'; // Import library GSAP utama untuk animasi
import { ScrollTrigger } from 'gsap/ScrollTrigger'; // Import plugin ScrollTrigger untuk animasi saat elemen masuk viewport

// Registrasi plugin ScrollTrigger ke dalam GSAP
gsap.registerPlugin(ScrollTrigger);

export default {
    name: 'Header',

    mounted() {
        // Animasi logo header: muncul dari atas dengan fade in
        this.$nextTick(() => {
            gsap.fromTo(this.$refs.logoheader,
                { opacity: 0, y: -100 },
                {
                    opacity: 1,
                    y: 0,
                    duration: 1.5,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: this.$refs.logoheader,
                        start: 'top 95%',
                        toggleActions: 'play reverse play reverse',
                    }
                }
            );
        });

        // Animasi judul header: muncul dari kanan dengan fade in
        this.$nextTick(() => {
            gsap.fromTo(this.$refs.titleheader,
                { opacity: 0, x: 100 },
                {
                    opacity: 1,
                    x: 0,
                    duration: 1.5,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: this.$refs.titleheader,
                        start: 'top 95%',
                        toggleActions: 'play reverse play reverse',
                    }
                }
            );
        });

        // Animasi deskripsi & logo media sosial: muncul dari bawah dengan fade in
        this.$nextTick(() => {
            gsap.fromTo(this.$refs.headerbottom,
                { opacity: 0, y: 100 },
                {
                    opacity: 1,
                    y: 0,
                    duration: 1.5,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: this.$refs.headerbottom,
                        start: 'top 95%',
                        toggleActions: 'play reverse play reverse',
                    }
                }
            );
        });

        // Animasi panah: memantul terus menerus ke atas-bawah
        gsap.to(this.$refs.arrowdown, {
            scale: 0.5,
            y: -60,
            duration: 1,
            ease: 'ease.out',
            repeat: -1,
            yoyo: true
        });

        // Gunakan ScrollTrigger untuk memastikan animasi hanya berjalan saat elemen masuk ke viewport
        // 'start: top 95%' berarti animasi akan mulai saat bagian atas elemen menyentuh 95% dari tinggi layar
    }
}
</script>

<template>
    <div class="header-container">
        <div class="header-wrapper">
            <div class="header-top">
                <img ref="logoheader" class="kucing-header kucing-header-1" src="../assets/images/kucing-header-1.svg"
                    alt="">
                <h1 ref="titleheader" class="header-title">Innovative Solutions for Animals</h1>
            </div>
            <div ref="headerbottom" class="header-bottom">
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
        <div class="header-arrow-down">
            <img ref="arrowdown" class="arrow-down" src="../assets/images/arrow.png" alt="">
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

.arrow-down {
    rotate: 270deg;
    position: absolute;
    bottom: 2vw;
    width: 2vw;
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

    .arrow-down {
        bottom: 6vw;
        width: 4vw;
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

    .arrow-down {
        bottom: 6vw;
        width: 6vw;
    }

}
</style>
