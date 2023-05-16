<template>
    <div class="about-page">
        <div class="about-content">
            <picture>
                <source media="(max-width: 767px)" srcset="assets/about/mobile/image-hero.jpg">
                <source media="(max-width: 1439px)" srcset="assets/about/tablet/image-hero.jpg">
                <source media="(max-width: 1440px)" srcset="assets/about/desktop/image-hero.jpg">
                <img src="assets/about/desktop/image-hero.jpg" alt="">
            </picture>
            <div class="about-text">
                <div class="text-container">
                    <h2>Your team of professionals</h2>
                    <p>Our small team of world-class professionals will work with you every step of the way. Strong relationships are at the core of everything we do. This extends to the relationship our projects have with their surroundings.</p>
                </div>
                <div class="text-container">
                    <h2>Our heritage</h2>
                    <p>Founded in 2007, we started as a trio of architects. Our complimentary skills and relentless attention to detail turned Arch into one of the most sought after boutique firms in the country.</p>
                    <p>Speciliazing in Urban Design allowed us to focus on creating exceptional structures that live in harmony with their surroundings. We consider every detail from every surrounding element to inform our designs. </p>
                    <p>Our small team of world-class professionals provides input on every project.</p>
                </div>
            </div>
            <div class="about-leaders">
                <h2>The leaders</h2>
                <div class="leader">

                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {

    }
    @media screen and (min-width: 768px) {

    }
    @media screen and (min-width: 1440px) {

    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'AboutPage',
        data: () => {
            return {

            }
        }
    })
</script>