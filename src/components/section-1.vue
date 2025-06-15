<script>
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

export default {
    name: 'Section1',
    mounted() {
        this.$nextTick(() => {
            gsap.fromTo(this.$refs.youtube,
                { opacity: 0, y: 100 },
                {
                    opacity: 1,
                    y: 0,
                    duration: 0.8,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: this.$refs.youtube,
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
    <div class="section1-container">
        <div class="section1">
            <div class="section1-1">
                <h1>We are</h1>
                <h3>
                    team of like-minded people, socially active companies, media personalities,
                    volunteers who help low-income shelters and foster carers to support homeless animals.
                </h3>
            </div>
            <div class="section1-2">
                <h1>Our primary goal</h1>
                <h3>
                    is to provide animals with the most necessary things - food, medicine,
                    and urgent needs for the livelihood of shelters. We believe in our power
                    and the power of conscious citizens who care about the environment and their health,
                    who understand the importance of helping each other, especially our little friends.
                    Growth begins with your care for your loved ones. Animals are one of the closest creatures to
                    humans
                    who remain with us throughout our lives.
                    We all know the healing power of warmth, grace, and big loving eyes.
                </h3>
                <div class="section1-2-quotes">
                    <div class="section1-2-vertical-line"></div>
                    <div>
                        <h3>"Animals need to have friends. Just like humans."</h3>
                        <h3>- James Herriot, All Creatures Great and Small</h3>
                    </div>
                </div>
                <h3>Who else if not we should support our younger brothers, especially in difficult times? Let's be
                    friends!</h3>
            </div>
            <div class="section1-3" ref="youtube">
                <iframe class="section1-3-iframe-youtube" src="https://www.youtube.com/embed/5Wk1rp99B7o">
                </iframe>
            </div>
        </div>
    </div>
</template>

<style>
/* section1 */

.section1 {
    display: flex;
    padding: 10vw;
    flex-direction: column;
    gap: 2.5vw;
}

.section1-1 {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.section1-2 {
    display: flex;
    flex-direction: column;
    gap: 2vw;
}

.section1-1 h1 {
    font-size: 4vw;
}

.section1-2-vertical-line {
    width: 4px;
    height: 10vw;
    background-color: pink;
    margin: 0 10px;
}

.section1-2-quotes {
    display: flex;
    flex-direction: row;
    gap: 1vw;
    align-items: center;
    margin-left: 2vw;
    font-style: italic;
}

.section1-1 h3 {
    font-size: 2.5vw;
    font-weight: 400;
    letter-spacing: 0.1vw;
    line-height: 4vw;
}

.section1-2 h1 {
    font-size: 4vw;
}

.section1-2 h3 {
    font-size: 2.5vw;
    font-weight: 400;
    letter-spacing: 0.1vw;
    line-height: 4vw;
}

.section1-3 {
    display: flex;
    justify-content: center;
    align-items: center;
}

.section1-3-iframe-youtube {
    width: 100vw;
    height: 45vw;
}

@media only screen and (max-width: 480px) {

    .section1-1 h1 {
        font-size: 8vw;
    }

    .section1-1 h3 {
        font-size: 3.5vw;
        line-height: 5.5vw;
    }

    .section1-2 h1 {
        font-size: 8vw;
    }

    .section1-2 h3 {
        font-size: 3.5vw;
        line-height: 5.5vw;
    }

    .section1-2-vertical-line {
        height: 30vw;
    }

}
</style>
