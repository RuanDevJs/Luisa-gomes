<template>
  <header class="header">
      <div class="header-container">
          <div class="header-title">
              <h1 @click="active = !active">Luiza Gomes</h1>
          </div>
          <transition>
            <nav :class="{
                'header-nav': true,
                'active': active
            }">
              <ul>
                  <li>
                      <a href="#minhas-obras" @click.prevent="handleClick">Minhas Obras</a>
                  </li>
                  <li>
                      <a href="#portfolio" @click.prevent="handleClick">Portfólio</a>
                  </li>
                  <li>
                      <a href="#experiencia">Experiência</a>
                  </li>
                  <li>
                      <a href="#contato">Contato</a>
                  </li>
              </ul>
          </nav>
          </transition>
      </div>
  </header>
</template>

<script>
import { reactive, toRefs, ref } from 'vue';
export default {
    name: "Header",
    setup(){
        const methods = reactive({
            handleClick({ currentTarget, target }){
                const links = document.querySelectorAll(".header-nav ul li a");
                const getId = target.getAttribute('href');
                const elementDistance = document.querySelector(getId).offsetTop;

                links.forEach(el => el.classList.remove('actived'))
                currentTarget.classList.add('actived');

                window.scrollTo({
                    behavior: 'smooth',
                    top:  elementDistance
                })
            }
        });

        const active = ref(false);

        return { ...toRefs(methods), active }
    }
}
</script>

<style lang="scss" scoped>

.header {
    padding: 20px;

    @media screen and (max-width: 728px){
        padding: 32px;
    }
}

.header-container {
    max-width: 960px;
    margin: 0 auto;

    display: flex;
    flex-wrap: wrap;
    align-items: center;
    align-content: center;
    justify-content: space-between;

    @media screen and (max-width: 728px){
        justify-content: center;
    }

    .header-title {
        h1 {
            font-size: 32px;
            font-weight: 700;
            color: #1f1f1f;

            cursor: pointer;
            padding: 12px;
            transition: .3s ease-in-out;

            @media screen and (max-width: 728px){
                text-align: center;
            }
        }

        h1:hover {
            color: #333;
        }

        @media screen and (max-width: 728px){
            width: 100%;
            justify-content: center;
        }
    }

    .header-nav {

        ul {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            align-content: center;
        }

        @media screen and (max-width: 728px){
            display: none;
        }

        li {
            margin: 0 5px;

            @media screen and (max-width: 728px){
                width: 100%;
            }
        }

        a {
            font-size: 16px;
            font-weight: 400;

            display: block;
            padding: 12px;
            color: #333;

            transition: .3s ease-in-out;
        }

        a:hover {
            color: #1f1f1f;
        }

        a.actived {
            font-weight: 400;
            color: #1f1f1f;
            border-bottom: 2px solid #1f1f1f;
            transition: .5s ease-in-out;
        }
    }

    nav.active {
     display: flex !important;

        @media screen and (max-width: 728px){
            display: flex !important;
            animation: Menu .5s forwards alternate;
        }
    }
}

@keyframes Menu {
    from {
        opacity: 0;
        transform: translate3d(0, -20px, 0);
    }
    to{
        opacity: 1;
        transform: translate3d(0, 0px, 0);
    }
}

</style>
