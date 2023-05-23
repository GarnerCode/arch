<template>
    <div class="about-page">
        <div class="hero-container">
            <picture class="hero-img">
                <source media="(max-width: 767px)" srcset="assets/about/mobile/image-hero.jpg">
                <source media="(max-width: 1439px)" srcset="assets/about/tablet/image-hero.jpg">
                <source media="(min-width: 1440px)" srcset="assets/about/desktop/image-hero.jpg">
                <img src="assets/about/desktop/image-hero.jpg" alt="">
            </picture>
            <div class="hero-text">
                <h1>About</h1>
                <h2>Your team of professionals</h2>
                <p>Our small team of world-class professionals will work with you every step of the way. Strong relationships are at the core of everything we do. This extends to the relationship our projects have with their surroundings.</p>
            </div>
        </div>
        <div class="heritage-container">
            <div class="heritage-text">
                <h2>Our<br/> Heritage</h2>
                <div class="heritage-paragraphs">
                    <p>Founded in 2007, we started as a trio of architects. Our complimentary skills and relentless attention to detail turned Arch into one of the most sought after boutique firms in the country.</p>
                    <p>Specializing in Urban Design allowed us to focus on creating exceptional structures that live in harmony with their surroundings. We consider every detail from every surrounding element to inform our designs. </p>
                    <p>Our small team of world-class professionals provides input on every project.</p>
                </div>
            </div>
            <img class="heritage-img" src="assets/about/desktop/image-heritage.jpg" alt="">
        </div>
        <div class="leaders-container">
            <h2>The<br/> Leaders</h2>
            <div class="leader-items">
                <div class="leader" v-for="(leader, index) of leaderData" :key="index">
                    <img class="leader-img" :src="leader.imageUrl" :alt="`${leader.name} headshot`">
                    <div class="leader-text">
                        <h4>{{ leader.name }}</h4>
                        <p>{{ leader.title }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        .about-page {
            display: flex;
            flex-direction: column;
            gap: 20rem;
            .hero-container {
                position: relative;
            }
            .hero-img {
                width: 100%;
                img {
                    width: 100%;
                }
            }
            .hero-text {
                position: relative;
                bottom: 10rem;
                background-color: white;
                padding: 10rem 5rem;
                padding-bottom: 0;
                width: 75%;
                h1 {
                    display: none;
                }
            }
            .heritage-container {
                padding: 0 var(--mobile-x-padding);
            }
            .heritage-img {
                display: none;
            }
            .leaders-container {
                padding: 0 var(--mobile-x-padding);
                display: flex;
                flex-direction: column;
                gap: 9rem;
            }
            .leader-items {
                display: flex;
                flex-direction: column;
                gap: 10rem;
            }
            .leader-img {
                width: 100%;
            }
            .leader-text {
                margin-top: 3rem;
                p {
                    margin: 0;
                    margin-top: 1rem;
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        .about-page {
            padding: 0 var(--tablet-x-padding);
            .hero-text {
                position: absolute;
                bottom: 0;
                right: 0;
                h1 {
                    display: block;
                    position: absolute;
                    top: -7rem;
                    right: 0;
                }
                h2 {
                    margin-top: 10rem;
                    font-size: 72px;
                }
            }
            .heritage-container {
                padding: 0;
                h2 {
                    font-size: 72px;
                }
            }
            .leaders-container {
                padding: 0;
                h2 {
                    font-size: 72px;
                }
            }
            .leader-items {
                display: grid;
                grid-template-columns: 1fr 1fr;
                column-gap: 1rem;
            }
            .leader-img {
                width: 280px;
            }
        }
    }
    @media screen and (min-width: 1440px) {
        .about-page {
            padding: 0 var(--desktop-x-padding);
            .hero-container {
                display: flex;
                flex-direction: row;
            }
            .hero-img {
                img {
                    width: 635px;
                }
            }
            .hero-text {
                width: 600px;
                padding-left: 0;
                padding-right: 0;
                margin: 0;
                h1 {
                    top: -10rem;
                    left: -5rem;
                }
                h2, p {
                    width: 446px;
                    margin-left: auto;
                }
            }
            .heritage-container {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                gap: 6rem;
            }
            .heritage-img {
                display: block;
            }
            .leaders-container {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
            }
            .leader-items {
                column-gap: 2rem;
            }
            .leader-img {
                width: 350px;
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { leaderData } from '@/const/leaderData';

    export default defineComponent({
        name: 'AboutPage',
        data: () => {
            return {
                leaderData,
            }
        }
    })
</script>