<template>
    <perzeption-page>
        <section class="perzeption-product">
            <div class="perzeption-product__content">
                <h1>
                    Our Product
                </h1>

                <div class="perzeption-product__features">
                    <swiper class="swiper" 
                    :options="swiperOption"
                    @click="nextSlide()">
                        <swiper-slide>
                        <img src="../assets/acuity.png" />
                        </swiper-slide>
                        <swiper-slide>
                        <img src="../assets/color.png" />
                        </swiper-slide>
                        <swiper-slide>
                        <img src="../assets/contrast.png" />
                        </swiper-slide>
                        <div class="swiper-pagination" slot="pagination"></div>
                    </swiper>

                    <div v-if="currSlide == 0">
                        <h2>FIND Vision Exam</h2>

                        <p>
                            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                            Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                            Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                            Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        </p>
                    </div>

                    <div v-if="currSlide == 1">
                        <h2>FIND Vision Exam</h2>

                        <p>
                            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                            Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                            Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                            Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        </p>
                    </div>

                    <div v-if="currSlide == 2">
                        <h2>FIND Vision Exam</h2>

                        <p>
                            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                            Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                            Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                            Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        </p>
                    </div>

                    <a href="/#/publication" target="_blank">View Publications</a>
                </div>
            </div>
        </section>
    </perzeption-page>
</template>

<script>
/**
 * The third section on the landing page.
 * Describes the various products PerZeption has to offer as a slideshow.
 */

// Dependency Components
import { Swiper, SwiperSlide } from 'vue-awesome-swiper';
import 'swiper/css/swiper.css';

// Components
import perzeptionPage from '@/components/perzeption-page.vue';

export default {
    name: 'perzeption-product',
    components: {
        Swiper,
        SwiperSlide,
        perzeptionPage
    },
    data() {
        return {
            currSlide: 0,
            swiperOption: {
                slidesPerView: 1,
                spaceBetween: 30,
                loop: true,
                autoplay: {
                    delay: 2500,
                    disableOnInteraction: false
                },
                pagination: {
                    el: '.swiper-pagination',
                    clickable: true
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev'
                }
            },
        }
    },
    methods: {
        /**
         * Sets the current index to the index of the slide in the gallery.
         * @returns void
         */
        nextSlide() {
            this.currSlide += 1;
            if (this.currSlide >= 3)
                this.currSlide = 0;
        }
    }

}
</script>

<style lang="scss">
@import '../styles/_base';

.perzeption-product {
    background-color: $perzeption-background-blue;
    padding: 80px;

    a {
        color: white;
        text-decoration: underline;
    }

    &__content {
        h1 {
            margin: unset;
        }
    }

    &__features {
        display: block;
        margin: 0 auto;
        width: 50vw;
        padding: 60px;
    }

    .swiper-slide {
        img {
            display: block;
            margin: 0 auto;
            object-fit: cover;
        }
    }
}
</style>