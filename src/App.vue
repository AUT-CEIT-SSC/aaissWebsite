<template>
    <div class="h-100">
        <vue-particles
                color="#b2b4ae"
                :particleOpacity="1"
                :particlesNumber="100"
                shapeType="circle"
                :particleSize="3"
                linesColor="#b2b4ae"
                :linesWidth="1"
                :lineLinked="true"
                :lineOpacity="1"
                :linesDistance="150"
                :moveSpeed="3"
                :hoverEffect="true"
                hoverMode="grab"
                :clickEffect="true"
                clickMode="push"
                class="particles"
        >
        </vue-particles><!-- stats - count particles -->
        <TopMenu></TopMenu>
        <transition name="fade" mode="out-in">
            <router-view/>
        </transition>
        <Footer></Footer>
    </div>
</template>

<script>
    import TopMenu from '@/components/TopMenu'
    import Footer from '@/components/Footer'

    export default {
        name: 'App',
        data: function () {
            return {}
        },
        components: {
            TopMenu, Footer
        }, methods: {},
        mounted() {
        }

    }
</script>

<style>
    *{
        scroll-behavior: smooth;
    }

    html, body {
        height: 100%;
    }

    .fade-enter-active,
    .fade-leave-active {
        transition-duration: 0.3s;
        transition-property: opacity;
        transition-timing-function: ease;
    }

    .fade-enter,
    .fade-leave-active {
        opacity: 0
    }

    div[style*="z-index: 10000"] {
        display: none !important;
    }

    .particles {
        position: fixed;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
    }
</style>
