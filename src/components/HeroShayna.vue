<template>
    <!-- Hero Section Begin -->
    <section class="hero-section">
        <carousel class="hero-items" :items="1" :nav="false" :autoplay="false" :loop="false" :dots="false" :mouseDrag="false">

            <div class="single-hero-items set-bg" style="background-image: url('img/hero-1.jpg')">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-5">
                            <span>Bag, kids</span>
                            <h1>Black friday</h1>
                            <p>
                                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore
                            </p>
                            <a href="#" class="primary-btn">Shop Now</a>
                        </div>
                    </div>
                </div>
            </div>
            <div class="single-hero-items set-bg" style="background-image: url('img/hero-2.jpg')">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-5">
                            <span>Bag,kids</span>
                            <h1>Black friday</h1>
                            <p>
                                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore
                            </p>
                            <a href="#" class="primary-btn">Shop Now</a>
                        </div>
                    </div>
                </div>
            </div>
            <div class="single-hero-items set-bg" style="background-image: url('img/hero-3.jpg')">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-5" style="margin-left: 700px;">
                            <span style="color: white;">Bag,kids</span>
                            <h1 style="color: white;">Black friday</h1>
                            <p style="color: white;">
                                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore
                            </p>
                            <a href="#" class="primary-btn">Shop Now</a>
                        </div>
                    </div>
                </div>
            </div>

        </carousel>
    </section>
    <!-- Hero Section End -->
</template>

<script>
import carousel from 'vue-owl-carousel'

export default {
    name: 'HeroShayna',
    components: {
        carousel
    }
}
</script>