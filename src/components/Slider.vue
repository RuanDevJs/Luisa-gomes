<template>
    <div class="slider">
        <div class="slide" v-for="(slide, index) of slides" :key="index">
            <div class="slide-img">
                <img :src="slide.source" alt="slide.name" draggable="false" />
            </div>
            <div class="slide-content">
                <h2> {{ slide.name }} </h2>
                <p> {{ slide.description }} </p>
                <a href="#" @click.prevent> Contratar </a>
            </div>
        </div>
        <div class="dots">
            <span></span>
            <span></span>
            <span></span>
        </div>
    </div>
</template>

<script>
import { onMounted, reactive, ref, toRefs, watch } from 'vue';
import beaches from "@/assets/slides/beaches.jpg";
import animals from "@/assets/slides/animals.jpg";
import graduatation from "@/assets/slides/graduatation.jpg";

export default {
    name: "Slider",
    setup(){
        const slides = ref([
            {
                name: 'Praia de Copacabana',
                description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam, eaque nulla beatae magni, saepe dolor aperiam similique ad enim, architecto quisquam eligendi aspernatur nobis! Cupiditate expedita minima quaerat similique sint.",
                source: beaches
            },
            {
                name: 'Animais',
                description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam, eaque nulla beatae magni, saepe dolor aperiam similique ad enim, architecto quisquam eligendi aspernatur nobis! Cupiditate expedita minima quaerat similique sint.",
                source: animals
            },
            {
                name: 'Formaturas de Engenharia de Software - Puc Minas',
                description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam, eaque nulla beatae magni, saepe dolor aperiam similique ad enim, architecto quisquam eligendi aspernatur nobis! Cupiditate expedita minima quaerat similique sint.",
                source: graduatation
            }
        ]);
        const counter = ref(0);

        const methods = reactive({
            timer(){
                setInterval(() => {
                    counter.value++;
                }, 5000);
            },
            handleSlide(){
                const slide = document.querySelectorAll('.slide');
                slide[counter.value].classList.add('active');

                const dots = document.querySelectorAll('.dots span');
                dots[counter.value].classList.add('active-dots');

                this.timer();
            }
        })

        onMounted(() => {
            methods.handleSlide();
        })

        watch(counter, (value) => {
            const slide = document.querySelectorAll('.slide');
            const dots = document.querySelectorAll('.dots span');
            // dots[counter.value].classList.add('active-dots');

            slide.forEach((el) => {
                el.classList.remove('active');
            });

            dots.forEach((el) => {
                el.classList.remove('active-dots');
            })

            if(value > 2){
                counter.value = 0;
            }else if(value < 0){
                counter.value = 2;
            }

            slide[counter.value].classList.add('active');
            dots[counter.value].classList.add('active-dots');
        })

        return {
            slides,
            ...toRefs(methods)
        }
    }
}
</script>

<style lang="scss" scoped>
    .slider {
        margin: 12px 0;
    }

    .slide {
        max-width: 960px;
        margin: 0 auto;

        display: none;
        flex-wrap: wrap;
        align-content: center;
        justify-content: center;
    }

    .slide.active {
        display: flex;
        animation: Next 1.2s forwards;
    }

    .slide-img img {
        display: block;
        width: 460px;
        height: 260px;
        object-fit: cover;
        border-radius: 12px;
    }

    .slide-content {
        flex: 1;
        margin-left: 25px;

        h2 {
            font-weight: 500;
            font-size: 32px;
            color: #1f1f1f;
            line-height: 1.3em;
        }

        p {
            margin: 12px 0;
            font-weight: 400;
            font-size: 14px;
            color: #c2c2c2;
            line-height: 1.5em;
        }

        a {
            display: block;
            margin: 32px 0;
            padding: 4px;
            width: 260px;

            background: #7026F5;
            border-radius: 170px 12px;
            text-align: center;

            font-size: 22px;
            font-weight: 400;
            color: #f9f9f9;
            transition: .5s ease-in-out;
        }

        a:hover {
            background: #7056F8;
        }
    }

    .dots {
        max-width: 100px;
        margin: 50px auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;

        span {
            display: block;
            width: 15px;
            height: 15px;
            margin: 0 auto;
            border-radius: 50px;
            background: #c2c2c2;
            transition: .3s ease-in-out;
        }

        span.active-dots {
            background: #7026F5;
        }
    }

    @keyframes Next {
        from {
            opacity: 0;
            transform: translate3d(0, 50px, 0);
        }
        to {
            opacity: 1;
            transform: translate3d(0, 0, 0);
        }
    }
</style>
