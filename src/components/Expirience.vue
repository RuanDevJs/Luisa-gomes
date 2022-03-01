<template>
  <section class="experience">
      <div class="experience-container">
          <div class="title">
              <h1>Experiência</h1>
          </div>
          <div class="select">
              <button class="select-btn">
                  <span @click="handleClick('Academic', $event)"> Experiência Acadêmica </span>
              </button>
               <button class="select-btn">
                  <span @click="handleClick('Profissional', $event)"> Experiência Profissional </span>
              </button>
          </div>
      </div>
     <transition mode="out-in">
        <component :is="isComponent" />
     </transition>
  </section>
</template>

<script>
import { reactive, ref, toRefs } from 'vue';

import Academic from './Academic.vue'
import Profissional from './Profissional.vue'

export default {
  components: { Academic, Profissional },
  emits: [],
  setup(){
      const isComponent = ref('');

      const methods = reactive({
          handleClick(value, { target }){
              const btn = document.querySelectorAll('.select-btn');
              btn.forEach(el => el.classList.remove('actived'));

              target.parentElement.classList.add('actived');
              isComponent.value = value
          }
      });

      return {
          ...toRefs(methods),
          isComponent
      }
  }
}
</script>

<style lang="scss" scoped>
    .experience {
        margin: 120px 0;
        padding: 50px 0;
    }

    .experience-container {
        max-width: 960px;
        margin: 0 auto;

        display: flex;
        flex-wrap: wrap;
        align-content: center;
        align-items: center;
        justify-content: space-between;
    }

    .title {
        max-width: 100%;
    }

    .title h1{
        font-size: 50px;
        color: #d9d9d9;
    }

    .select {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        gap: 20px;


        button {
            position: relative;
            background: #f9f9f9;

            padding: 28px;
            width: 320px;

            border: 0;
            outline: 0;

            border-radius: 4px;
            box-shadow: 0px 0px 8px rgba(0,0,0,0.2);
            cursor: pointer;
            transition: .2s ease-in-out;

            span {
                display: flex;
                justify-content: center;
                align-items: center;

                position: absolute;
                top: 0;
                left: 0;
                right: 0;
                bottom: 0;

                font-size: 18px;
                font-weight: 500;
                color: #333;
            }
        }

        button.actived {
            background: #7026F5;

            span {
                color: #E6E0F2;
            }
        }
    }

    .v-enter-active {
        animation: Animation .5s forwards;
    }

    @keyframes Animation {
        from {
            opacity: 0;
            transform: translate3d(-50px,0,0);
        }

        to {
            opacity: 1;
            transform: translate3d(0px,0,0);
        }
    }
</style>
