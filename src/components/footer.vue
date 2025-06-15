<script>
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);
export default {
    name: 'Footer',
    mounted() {
        this.$nextTick(() => {
            gsap.fromTo(this.$refs.footerimage,
                { opacity: 0, x: -100 },
                {
                    opacity: 1,
                    x: 0,
                    duration: 0.8,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: this.$refs.footerimage,
                        start: 'top 95%',
                        toggleActions: 'play reverse play reverse',
                    }
                }
            );
        });
    }
}

</script>


<template>
    <div class="footer-container">
        <div class="footer">
            <div class="footer-left">
                <div class="footer-description">
                    <h1>Contact us</h1>
                    <h3>Kyiv, Ukraine</h3>
                    <h3>mail@isa.co.ua</h3>
                </div>
                <div class="footer-logo">
                    <img class="logo" src="../assets/images/youtube.svg" alt="youtube">
                    <img class="logo" src="../assets/images/instagram.svg" alt="instagram">
                    <img class="logo" src="../assets/images/facebook.svg" alt="facebook">
                    <img class="logo" src="../assets/images/patreon.svg" alt="patreon">
                    <img class="logo" src="../assets/images/telegram.svg" alt="telegram">
                </div>
            </div>
            <div ref="footerimage" class="footer-right">
                <img src="../assets/images/footer-image.svg" alt="">
            </div>
        </div>
    </div>
</template>


<style>
.footer-container {
    background-color: var(--quaternaryColor);
}

.footer {
    padding: 10vw;
    display: flex;
    flex-direction: row;
    gap: 4vw;
    justify-content: space-between;
    align-items: center;
}

.footer-left {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.footer-description h1 {
    font-size: 4vw;
}

.footer-description h3 {
    font-size: 2.2vw;
    font-weight: 400;
    letter-spacing: 0.1vw;
    line-height: 3.5vw;
}

.footer-logo {
    display: flex;
    flex-direction: row;
    gap: 1.2vw;
}

.footer-logo img {
    width: 3vw;
}

.footer-right img {
    width: 40vw;
    height: auto;
}

.logo {
    transition: ease 0.3s;
}

.logo:hover {
    transform: scale(80%);
    transition: ease 0.3s;
}

@media only screen and (max-width: 480px) {

    .footer {
        justify-content: start;
        align-items: start;
        flex-direction: column;
        gap: 15vw;
    }

    .footer-left {
        display: flex;
        flex-direction: column;
        gap: 9vw;
    }

    .footer-description h1 {
        font-size: 8vw;
    }

    .footer-description h3 {
        font-size: 3.5vw;
        line-height: 5vw;
    }

    .footer-logo {
        gap: 3vw;
    }

    .footer-logo img {
        width: 8vw;
    }

    .footer-right img {
        width: 80vw;
        height: auto;
    }

}
</style>
