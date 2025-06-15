<script>
import { gsap } from 'gsap'; // Import library GSAP utama untuk animasi
import { ScrollTrigger } from 'gsap/ScrollTrigger'; // Import plugin ScrollTrigger untuk animasi saat elemen masuk viewport
import { cardsSection6 } from './fetchAPIData';

// Registrasi plugin ScrollTrigger ke dalam GSAP
gsap.registerPlugin(ScrollTrigger);

export default {
    name: 'Section-6',

    // Mengambil data yang dibutuhkan untuk section 6
    data() {
        return {
            cardsSection6: cardsSection6
        }
    },
    mounted() {
        // Animasi logo: muncul dari bawah dengan fade in. Jika viewport dari bawah, maka akan fade in dari atas
        this.$nextTick(() => {
            this.$refs.cardpartners.forEach((cardpartner) => {
                gsap.from(cardpartner, {
                    opacity: 0,
                    y: 100,
                    duration: 0.8,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: cardpartner,
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
    <div class="section6-container">
        <div class="section6">
            <div class="section6-top">
                <h1>Our partners</h1>
                <h3>are take care of our fund and help us with many questions</h3>
            </div>
            <div class="section6-bottom">
                <div ref="cardpartners" class="card-wrapper-section6 card-wrapper-outer" v-for="item in cardsSection6"
                    :key="item.id">
                    <div class="card-wrapper-inner-section6">
                        <img class="section6-card-image" :src="item.image" alt="">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.section6-container {
    background-color: white;
}

.section6 {
    padding: 10vw;
    display: flex;
    flex-direction: column;
    gap: 4vw;
}

.section6-top {
    display: flex;
    flex-direction: column;
    gap: 1.5vw;
}

.section6-top h1 {
    font-size: 4vw;
}

.section6-top h3 {
    font-size: 2.4vw;
    font-weight: 400;
    letter-spacing: 0.1vw;
    line-height: 4vw;
}

.section6-bottom {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 3.6vw;
}

.card-wrapper-section6 {
    display: flex;
    justify-content: center;
    align-items: center;
}

.card-wrapper-inner-section6 {
    display: flex;
    gap: 8px;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.section6-card-image {
    filter: grayscale(100%);
    max-width: 17vw;
}

@media only screen and (max-width: 900px) {

    .section6 {
        gap: 4vw;
    }

    .section6-top {
        gap: 2vw;
    }

    .section6-bottom {
        gap: 5vw;
        row-gap: 5vw;
    }

    .section6-card-image {
        max-width: 23vw;
    }

}

@media only screen and (max-width: 480px) {

    .section6 {
        gap: 8vw;
    }

    .section6-top {
        gap: 3vw;
    }

    .section6-top h1 {
        font-size: 8vw;
    }

    .section6-top h3 {
        font-size: 3.8vw;
        font-weight: 400;
        letter-spacing: 0.1vw;
        line-height: 4vw;
    }

    .section6-bottom {
        gap: 8vw;
        row-gap: 5vw;
    }

    .section6-card-image {
        max-width: 35vw;
    }

}
</style>
