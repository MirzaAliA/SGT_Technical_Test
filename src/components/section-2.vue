<script>
import { cardsSection2 } from './fetchAPIData';
import { gsap } from 'gsap'; // Import library GSAP utama untuk animasi
import { ScrollTrigger } from 'gsap/ScrollTrigger'; // Import plugin ScrollTrigger untuk animasi saat elemen masuk viewport

// Registrasi plugin ScrollTrigger ke dalam GSAP
gsap.registerPlugin(ScrollTrigger);

export default {
    name: 'Section2',

    // Mengambil data yang dibutuhkan untuk section 2
    data() {
        return {
            cardsSection2: cardsSection2
        }
    },
    mounted() {
        // Animasi card: muncul dari kiri dengan fade in
        this.$nextTick(() => {
            this.$refs.projects.forEach((project) => {
                gsap.fromTo(project,
                    { opacity: 0, x: -100 },
                    {
                        opacity: 1,
                        x: 0,
                        duration: 0.8,
                        ease: 'power2.out',
                        scrollTrigger: {
                            trigger: project,
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
    <div class="section2-container">
        <div class="section2">
            <div class="section2-1">
                <h1>Our projects</h1>
                <h3>
                    are very different in terms of priority, scale and complexity of implementation
                </h3>
            </div>
            <div class="section2-2">
                <div :class="`card-wrapper-section2 card-wrapper-outer-${index + 1}`"
                    v-for="(item, index) in cardsSection2" :key="item.id" ref="projects">
                    <div class="card-wrapper-inner-section2">
                        <h1>{{ item.title }}</h1>
                        <h3>{{ item.description }}</h3>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style>
/* section2 */

.section2-container {
    background-color: var(--secondaryColor);
}

.section2 {
    padding: 10vw;
    display: flex;
    flex-direction: column;
    gap: 2.5vw;
    color: white;
}

.section2-1 {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.section2-1 h1 {
    font-size: 4vw;
}

.section2-1 h3 {
    font-size: 2.5vw;
    font-weight: 400;
    letter-spacing: 0.1vw;
    line-height: 4vw;
}

.section2-2 {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.card-wrapper-inner-section2 {
    padding: 4vw 6vw 4vw 3.5vw;
    display: flex;
    flex-direction: column;
    gap: 1vw;
    border-style: solid;
    border-width: 3.5px;
    background-color: transparent;
    transition: ease 0.3s;
}

.card-wrapper-inner-section2 h1 {
    font-size: 3vw;
}

.card-wrapper-inner-section2 h3 {
    font-size: 2vw;
    font-weight: 400;
}

.card-wrapper-outer-1 {
    background-color: black;
}

.card-wrapper-outer-2 {
    background-color: #31be32;
}

.card-wrapper-outer-3 {
    background-color: #ff97d0;
}

.card-wrapper-section2:hover .card-wrapper-inner-section2 {
    transform: translate(1vw, -1vw);
    transition: ease 0.3s;
}

@media only screen and (max-width: 900px) {

    .card-wrapper-inner-section2 {
        padding: 7vw 6vw 7vw 7vw;
        gap: 2vw;
        border-style: solid;
        border-width: 3.5px;
    }

    .card-wrapper-inner-section2 h1 {
        font-size: 3.5vw;
    }

    .card-wrapper-inner-section2 h3 {
        font-size: 2.5vw;
        font-weight: 400;
    }

    .section2-2 {
        gap: 4vw;
    }

    .card-wrapper-section2:hover .card-wrapper-inner-section2 {
        transform: translate(1.5vw, -1.5vw);
    }

}

@media only screen and (max-width: 480px) {

    .section2 {
        gap: 7vw;
    }

    .section2-1 h1 {
        font-size: 8vw;
    }

    .section2-1 h3 {
        font-size: 3.5vw;
        font-weight: 400;
        letter-spacing: 0.1vw;
        line-height: 4vw;
    }

    .card-wrapper-inner-section2 {
        padding: 8vw 10vw 8vw 10vw;
        gap: 2vw;
        border-style: solid;
        border-width: 3.5px;
    }

    .card-wrapper-inner-section2 h1 {
        font-size: 6vw;
    }

    .card-wrapper-inner-section2 h3 {
        font-size: 3.9vw;
        font-weight: 400;
    }

    .section2-2 {
        gap: 6vw;
    }

    .card-wrapper-section2:hover .card-wrapper-inner-section2 {
        transform: translate(2vw, -2vw);
    }
}
</style>
