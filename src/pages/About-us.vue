<script>
import Footer from '../components/footer.vue';
import Header from '../components/header.vue';
import Section1 from '../components/section-1.vue';
import Section2 from '../components/section-2.vue';
import Section3 from '../components/section-3.vue';
import Section4 from '../components/section-4.vue';
import Section5 from '../components/section-5.vue';
import Section6 from '../components/section-6.vue';
import FloatingButton from '../components/floating-button.vue';

export default {
    // data() {
    //     return {
    //         name: 'Mirza Ali'
    //     }
    // },
    components: {
        Header,
        Section1,
        Section2,
        Section3,
        Section4,
        Section5,
        Section6,
        Footer,
        FloatingButton
    }
}
</script>

<template>
    <FloatingButton />
    <Header />
    <Section1 />
    <Section2 />
    <Section3 />
    <Section4 />
    <Section5 />
    <Section6 />
    <Footer />
    
    
</template>

<style scoped>
.logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
}

.logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
    filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
