<template>
    <section id="landing">
            <picture class="hero-img">
                <source media="(max-width: 767px)" srcset="assets/home/mobile/image-hero-paramour.jpg">
                <source media="(max-width: 1439px)" srcset="assets/home/tablet/image-hero-paramour.jpg">
                <source media="(min-width: 1440px)" srcset="assets/home/desktop/image-hero-paramour.jpg">
                <img src="assets/home/desktop/image-hero-paramour.jpg" alt="Project Paramour facade">
            </picture>
            <div class="landing-content">
                <div class="landing-text">
                    <h2>Project Paramour</h2>
                    <p>Project made for an art museum near Southwest London. Project Paramour is a statement of bold, modern architecture.</p>
                </div>
                <button class="button button-default">
                    See Our Portfolio
                    <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="white" stroke-width="2"/><path d="M0 10H24" stroke="white" stroke-width="2"/></svg>
                </button>
            </div>
        <Slideshow></Slideshow>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #landing {
            position: relative;
            .hero-img {
                filter: var(--image-filter);
                display: block;
                img {
                    width: 100%;
                }
            }
            .landing-content {
                position: absolute;
                top: 0;
                height: 100%;
                padding: 0 var(--mobile-x-padding);
                display: flex;
                flex-direction: column;
                justify-content: center;
                gap: 5rem;
                h2, p {
                    color: white;
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        #landing {
            padding: 0 var(--tablet-x-padding);
            display: flex;
            flex-direction: column;
            align-items: center;
            .landing-content {
                width: calc(573px - 20rem);
            }
        }
    }
    @media screen and (min-width: 1440px) {
        #landing {
            .hero-img, .landing-content {
                display: none;
            }
        }
    }
</style>