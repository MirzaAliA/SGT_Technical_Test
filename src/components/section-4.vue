<script>
import { gsap } from 'gsap'; // Import library GSAP utama untuk animasi
import { ScrollTrigger } from 'gsap/ScrollTrigger'; // Import plugin ScrollTrigger untuk animasi saat elemen masuk viewport

// Registrasi plugin ScrollTrigger ke dalam GSAP
gsap.registerPlugin(ScrollTrigger);

import { cardsSection4 } from './fetchAPIData';
export default {
    name: 'Section-4',

    // Mengambil data yang dibutuhkan untuk section 4
    data() {
        return {
            cardsSection4: cardsSection4
        };
    },
    mounted() {
        // Animasi card: muncul dari bawah dengan fade in. Jika viewport dari bawah, maka akan fade in dari atas
        this.$nextTick(() => {
            this.$refs.cardteams.forEach((cardteam) => {
                gsap.from(cardteam, {
                    opacity: 0,
                    y: 100,
                    duration: 0.8,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: cardteam,
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
    <div class="section4-container">
        <div class="section4">
            <div class="section4-top">
                <h1>Our team</h1>
                <h3>consists of completely different people who are united by a common desire - to help</h3>
            </div>
            <div class="section4-bottom">
                <div ref="cardteams" class="card-wrapper-section4 card-wrapper-outer" v-for="item in cardsSection4"
                    :key="item.id">
                    <div class="card-wrapper-inner-section4">
                        <img class="section4-card-image" :src="item.image" alt="">
                        <h3>{{ item.name }}</h3>
                        <p>{{ item.description }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style>
.section4-container {
    background-color: white;
}

.section4 {
    padding: 10vw;
    display: flex;
    flex-direction: column;
    gap: 4vw;
}

.section4-top {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.section4-top h1 {
    font-size: 4vw;
}

.section4-top h3 {
    font-size: 2.5vw;
    font-weight: 400;
    letter-spacing: 0.1vw;
    line-height: 4vw;
}

.card-wrapper-section4 {
    width: 17vw;
    height: 30vw;
    background-color: var(--primaryAccsent);
}

.section4-bottom {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 3.6vw;
}

.card-wrapper-inner-section4 {
    display: flex;
    width: 17vw;
    height: 30vw;
    padding: 2vw;
    gap: 20px;
    flex-direction: column;
    align-items: center;
    text-align: center;
    border-style: solid;
    border-color: black;
    border-width: 3.5px;
    transition: ease 0.3s;
}

.card-wrapper-inner-section4 h3 {
    margin-top: 10px;
    font-size: 1.4vw;
    font-weight: 500;
}

.card-wrapper-inner-section4 p {
    font-size: 1.2vw;
    font-weight: 400;
}

.section4-card-image {
    filter: grayscale(100%);
    width: 13vw;
    height: 13vw;
}

.card-wrapper-section4:hover .card-wrapper-inner-section4 {
    transform: scale(90%);
    transition: ease 0.3s;
}

@media only screen and (max-width: 900px) {

    .card-wrapper-section4 {
        width: 24vw;
        height: 46vw;
    }

    .section4-bottom {
        gap: 3.6vw;
    }

    .card-wrapper-inner-section4 {
        width: 24vw;
        height: 46vw;
        padding: 2vw;
        gap: 20px;
    }

    .card-wrapper-inner-section4 h3 {
        margin-top: 10px;
        font-size: 2.5vw;
    }

    .card-wrapper-inner-section4 p {
        font-size: 1.8vw;
    }

    .section4-card-image {
        width: 17vw;
        height: 17vw;
    }

}

@media only screen and (max-width: 480px) {

    .section4 {
        gap: 8vw;
    }

    .section4-top h1 {
        font-size: 8vw;
    }

    .section4-top h3 {
        font-size: 3.5vw;
    }

    .card-wrapper-section4 {
        width: 35vw;
        height: 62vw;
    }

    .section4-bottom {
        justify-content: space-between;
        gap: 9vw;
        row-gap: 7vw;
    }

    .card-wrapper-inner-section4 {
        width: 35vw;
        height: 62vw;
        padding: 4vw;
        gap: 10px;
    }

    .card-wrapper-inner-section4 h3 {
        margin-top: 10px;
        font-size: 3.5vw;
    }

    .card-wrapper-inner-section4 p {
        font-size: 2.4vw;
    }

    .section4-card-image {
        width: 27vw;
        height: 27vw;
    }
}
</style>
