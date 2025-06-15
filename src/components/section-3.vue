    <script>
    import { cardsSection3 } from './fetchAPIData'
    import { gsap } from 'gsap';
    import { ScrollTrigger } from 'gsap/ScrollTrigger';

    gsap.registerPlugin(ScrollTrigger);

    export default {
        name: 'Section-3',
        data() {
            return {
                cardsSection3: cardsSection3
            };
        },
        mounted() {
            this.$nextTick(() => {
                this.$refs.cards.forEach((cardEl) => {
                    gsap.from(cardEl, {
                        opacity: 0,
                        y: 100,
                        duration: 0.8,
                        ease: 'power2.out',
                        scrollTrigger: {
                            trigger: cardEl,
                            start: 'top 95%',
                            toggleActions: 'play reverse play reverse',
                        },
                    });
                });
            });

            this.$nextTick(() => {
                gsap.fromTo(this.$refs.help,
                    { opacity: 0, x: -100 },
                    {
                        opacity: 1,
                        x: 0,
                        duration: 0.8,
                        ease: 'power2.out',
                        scrollTrigger: {
                            trigger: this.$refs.help,
                            start: 'top 95%',
                            toggleActions: 'play reverse play reverse',
                        }
                    }
                );
            });
        },
    }

</script>



<template>
    <div class="section3-container">
        <div class="section3">
            <div class="section3-top">
                <h1>We want to help</h1>
                <h3>homeless packs, volunteers, guardians, overstayers, shelters and other organisations</h3>
            </div>
            <div class="section3-bottom">
                <div class="card-wrapper-section3 card-wrapper-outer" v-for="item in cardsSection3" :key="item.id"
                    ref="cards">
                    <div class="card-wrapper-inner-section3">
                        <h1>{{ item.title }}</h1>
                    </div>
                </div>

            </div>
            <div class="button-help-wrapper" ref="help">
                <div class="button-help">
                    <h1>apply for help</h1>
                    <img class="arrow-image" src="../assets/images/arrow.png" alt="">
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.section3-container {
    background-color: var(--primaryAccsent);
}

.section3 {
    padding: 10vw;
    display: flex;
    flex-direction: column;
    gap: 4vw;
}

.section3-top {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.section3-top h1 {
    font-size: 4vw;
}

.section3-top h3 {
    font-size: 2.5vw;
    font-weight: 400;
    letter-spacing: 0.1vw;
    line-height: 4vw;
}

.section3-bottom {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 3.5vw;
    row-gap: 5vw;
}

.card-wrapper-section3 {
    background-color: white;
}

.card-wrapper-inner-section3 {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2vw;
    width: 24vw;
    height: 6vw;
    border-style: solid;
    border-color: black;
    border-width: 3.5px;
    transition: ease 0.3s;
}

.card-wrapper-inner-section3 h1 {
    font-weight: 400;
    font-size: 1.5vw;
}

.button-help {
    display: flex;
    padding: 1.5vw;
    margin-top: 4vw;
    background-color: #fd95cf;
    width: 20vw;
    height: 5vw;
    gap: 1vw;
    justify-content: center;
    align-items: center;
    border-style: solid;
    border-color: black;
    border-width: 3.5px;
}

.button-help h1 {
    font-size: 1.8vw;
}

.button-help img {
    transition: ease 0.3s;
    width: 3vw;
    rotate: 180deg;
}

.card-wrapper-section3:hover .card-wrapper-inner-section3 {
    transform: translate(1vw, -1vw);
    transition: ease 0.3s;
}

.button-help:hover .arrow-image {
    transform: translateX(-0.5vw);
    transition: ease 0.3s;
}

@media only screen and (max-width: 900px) {

    .card-wrapper-inner-section3 {
        height: auto;
    }

    .section3-bottom {
        gap: 3.5vw;
        row-gap: 5vw;
    }

    .card-wrapper-inner-section3 {
        padding: 4vw 2vw 4vw 2vw;
        width: 38vw;
        height: 12vw;
    }

    .card-wrapper-inner-section3 h1 {
        font-weight: 400;
        font-size: 2.5vw;
        line-height: 5vw;
    }

    .button-help {
        padding: 1vw;
        margin-top: 4vw;
        width: 25vw;
        height: 7vw;
        gap: 1vw;
    }

    .button-help h1 {
        font-size: 2vw;
    }

    .button-help img {
        width: 3vw;
        rotate: 180deg;
    }

    .card-wrapper-section3:hover .card-wrapper-inner-section3 {
        transform: translate(1.5vw, -1.5vw);
    }

    .button-help:hover .arrow-image {
        transform: translateX(-1vw);
    }

}

@media only screen and (max-width: 480px) {

    .section3-top h1 {
        font-size: 8vw;
    }

    .section3-top h3 {
        font-size: 3.5vw;
        line-height: 6vw;
    }

    .card-wrapper-inner-section3 {
        height: auto;
    }

    .section3-bottom {
        justify-content: space-between;
        gap: 8vw;
        row-gap: 5vw;
    }

    .card-wrapper-inner-section3 {
        padding: 10vw 8vw 10vw 8vw;
        width: 35vw;
        height: 30vw;
    }

    .card-wrapper-inner-section3 h1 {
        font-weight: 400;
        font-size: 3.2vw;
        line-height: 5vw;
    }

    .button-help {
        padding: 1vw;
        margin-top: 4vw;
        width: 50vw;
        height: 13vw;
        gap: 4vw;
    }

    .button-help h1 {
        font-size: 3.5vw;
    }

    .button-help img {
        width: 4vw;
        rotate: 180deg;
    }

    .card-wrapper-section3:hover .card-wrapper-inner-section3 {
        transform: translate(3vw, -3vw);
    }

    .button-help:hover .arrow-image {
        transform: translateX(-1.5vw);
    }

}
</style>
