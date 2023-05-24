<template>
    <div class="contact-page">
        <div class="page-tag">
            <div class="tag-line"></div>
            <div class="tag-label">Contact</div>
        </div>
        <div class="hero-container">
            <picture class="hero-img">
                <source media="max-width(767px)" srcset="assets/contact/mobile/image-hero.jpg">
                <source media="max-width(1439px)" srcset="assets/contact/tablet/image-hero.jpg">
                <source media="min-width(1440px)" srcset="assets/contact/desktop/image-hero.jpg">
                <img src="assets/contact/desktop/image-hero.jpg" alt="">
                <div class="hero-text">
                    <h1>Contact</h1>
                    <h2>Tell us about your project</h2>
                    <p>We'd love to hear more about your project. Please, leave a message below or give us a call. We have two offices, one in Texas and one in Tennessee. If you find yourself nearby, come say hello!</p>
                </div>
            </picture>
        </div>
        <div class="details-container">
            <h2>Contact<br/> Details</h2>
            <div class="contact-detail">
                <p class="detail-label">Main Office</p>
                <div class="detail-values">
                    <div class="column-left">
                        <p>Mail: archone@mail.com</p>
                        <p>Address: 1892  Chenoweth Drive TN</p>
                        <p>Phone: 	123-456-3451</p>
                    </div>
                    <div class="column-right">
                        <button class="button button-secondary">
                            View on Map
                            <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="#1B1D23" stroke-width="2"/><path d="M0 10H24" stroke="#1B1D23" stroke-width="2"/></svg>
                        </button>
                    </div>
                </div>
            </div>
            <div class="contact-detail">
                <p class="detail-label">Office II</p>
                <div class="detail-values">
                    <div class="column-left">
                        <p>Mail: archtwo@mail.com</p>
                        <p>Address: 3399  Wines Lane TX</p>
                        <p>Phone: 832-123-4321</p>
                    </div>
                    <div class="column-right">
                        <button class="button button-secondary">
                            View on Map
                            <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="#1B1D23" stroke-width="2"/><path d="M0 10H24" stroke="#1B1D23" stroke-width="2"/></svg>
                        </button>
                    </div>
                </div>
            </div>
        </div>
        <Map></Map>
        <div class="form-container">
            <h2>Connect<br/> with us</h2>
            <form>
                <div class="field">
                    <input type="text" placeholder="Name">
                </div>
                <div class="field">
                    <input type="text" placeholder="Email">
                </div>
                <div class="field">
                    <textarea placeholder="Message"></textarea>
                    <button class="button button-default button-small">
                        <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="white" stroke-width="2"/><path d="M0 10H24" stroke="white" stroke-width="2"/></svg>
                    </button>
                </div>
            </form>
        </div>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        .contact-page {
            display: flex;
            flex-direction: column;
            gap: 10rem;
            .hero-container {
                position: relative;
            }
            .hero-img {
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
            }
            .details-container {
                padding: 0 var(--mobile-x-padding);
                h2 {
                    margin-bottom: 9rem;
                }
            }
            .detail-label {
                font-size: 18px;
                font-weight: bold;
                color: var(--color-dark-gray);
            }
            .column-left {
                p {
                    margin: 0;
                }
            }
            .form-container {
                padding: 0 var(--mobile-x-padding);
                h2 {
                    margin-bottom: 9rem;
                }
            }
            form {
                display: flex;
                flex-direction: column;
                gap: 7rem;
                .button {
                    margin-left: auto;
                    margin-right: 0;
                    position: relative;
                    bottom: 3px;
                }
            }
            input, textarea {
                resize: none;
                border: none;
                border-bottom: 1px solid var(--color-primary);
                padding: 2rem;
                font-size: 20px;
                font-weight: bold;
                width: calc(100% - 4rem);
                &::placeholder {
                    color: var(--color-light-gray);
                }
                &:focus {
                    outline: none;
                }
            }
            textarea {
                height: 92px;
            }
        }
    }
    @media screen and (min-width: 768px) {
        .contact-page {
            padding: 0 var(--tablet-x-padding);
            gap: 20rem;
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
                    font-size: 72px;
                }
            }
            .details-container {
                display: flex;
                flex-direction: column;
                gap: 5rem;
                padding: 0;
                h2 {
                    font-size: 72px;
                    margin: 0;
                }
            }
            .detail-values {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
            }
            .form-container {
                padding: 0;
            }
        }
    }
    @media screen and (min-width: 1440px) {
        .contact-page {
            padding: 0 var(--desktop-x-padding);
            .hero-container {
                display: flex;
                flex-direction: row;
            }
            .hero-text {
                width: 600px;
                padding-left: 0;
                padding-right: 0;
                h1 {
                    top: -10rem;
                    right: 0rem;
                }
                h2, p {
                    width: 446px;
                    margin-left: auto;
                }
            }
            .details-container {
                flex-direction: row;
                justify-content: space-between;
            }
            .detail-values {
                flex-direction: column;
            }
            .form-container {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                h2 {
                    margin: 0;
                }
            }
            form {
                width: 600px;
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'ContactPage',
        data: () => {
            return {

            }
        }
    })
</script>