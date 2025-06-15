<script>
import { gsap } from 'gsap'; // Import library GSAP utama untuk animasi
import { ScrollTrigger } from 'gsap/ScrollTrigger'; // Import plugin ScrollTrigger untuk animasi saat elemen masuk viewport
import { cardsSection5 } from './fetchAPIData';
// Registrasi plugin ScrollTrigger ke dalam GSAP
gsap.registerPlugin(ScrollTrigger);

export default {
    name: 'Section-5',

    // Mengambil data yang dibutuhkan untuk section 5
    data() {
        return {
            cardsSection5: cardsSection5
        }
    },
    mounted() {
        // Animasi card: muncul dari bawah dengan fade in. Jika viewport dari bawah, maka akan fade in dari atas
        this.$nextTick(() => {
            this.$refs.cardcitizens.forEach((cardcitizen) => {
                gsap.from(cardcitizen, {
                    opacity: 0,
                    y: 100,
                    duration: 0.8,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: cardcitizen,
                        start: 'top 95%',
                        toggleActions: 'play reverse play reverse',
                    },
                });
            });
        });
    },
}

</script>

<template>
    <div class="section5-container">
        <div class="section5">
            <div class="section5-top">
                <h1>Socially active citizens</h1>
                <h3>support us</h3>
            </div>
            <div class="section5-bottom">
                <div ref="cardcitizens" class="card-wrapper-section5 card-wrapper-outer" v-for="item in cardsSection5"
                    :key="item.id">
                    <div class="card-wrapper-inner-section5">
                        <img class="section5-card-image" :src="item.image" alt="">
                        <h3>{{ item.name }}</h3>
                        <p>{{ item.description }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.section5-container {
    background-color: var(--tertiaryColor);
}

.section5 {
    padding: 10vw;
    display: flex;
    flex-direction: column;
    gap: 4vw;
}

.section5-top {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.section5-top h1 {
    font-size: 4vw;
}

.section5-top h3 {
    font-size: 2.5vw;
    font-weight: 400;
    letter-spacing: 0.1vw;
    line-height: 4vw;
}

.card-wrapper-section5 {
    width: 17vw;
    height: 25vw;
}

.section5-bottom {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 3.6vw;
}

.card-wrapper-inner-section5 {
    display: flex;
    width: 17vw;
    height: 25vw;
    gap: 8px;
    flex-direction: column;
    align-items: center;
    text-align: center;
}

.card-wrapper-inner-section5 h3 {
    margin-top: 10px;
    font-size: 1.5vw;
    font-weight: 500;
}

.card-wrapper-inner-section5 p {
    margin-top: 8px;
    font-size: 1.2vw;
    font-weight: 400;
}

.section5-card-image {
    filter: grayscale(100%);
    width: 17.5vw;
    height: 17.5vw;
}

@media only screen and (max-width: 900px) {

    .card-wrapper-section5 {
        width: 23vw;
        height: 30vw;
    }

    .section5-bottom {
        margin-bottom: 4vw;
        gap: 4.5vw;
        row-gap: 9vw;
    }

    .card-wrapper-inner-section5 {
        width: 23vw;
        height: 30vw;
        gap: 8px;
    }

    .card-wrapper-inner-section5 h3 {
        margin-top: 10px;
        font-size: 2.5vw;
    }

    .card-wrapper-inner-section5 p {
        margin-top: 8px;
        font-size: 2vw;
    }

    .section5-card-image {
        width: 24vw;
        height: 24vw;
    }

}

@media only screen and (max-width: 480px) {

    .section5 {
        gap: 8vw;
    }

    .section5-top {
        gap: 3vw;
    }

    .section5-top h1 {
        font-size: 8vw;
    }

    .section5-top h3 {
        font-size: 3.5vw;
    }

    .card-wrapper-section5 {
        width: 35vw;
        height: 42vw;
    }

    .section5-bottom {
        justify-content: space-between;
        margin-bottom: 10vw;
        gap: 7.5vw;
        row-gap: 20vw;
    }

    .card-wrapper-inner-section5 {
        width: 35vw;
        height: 42vw;
        gap: 8px;
    }

    .card-wrapper-inner-section5 h3 {
        margin-top: 10px;
        font-size: 3.5vw;
    }

    .card-wrapper-inner-section5 p {
        margin-top: 8px;
        font-size: 3vw;
    }

    .section5-card-image {
        width: 36vw;
        height: 36vw;
    }
}
</style>
