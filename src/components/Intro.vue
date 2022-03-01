<template>
  <main class="intro">
      <div class="intro-container">
          <div class="intro-icon">
              <img src="@/assets/LuisaGomes.jpeg" alt="Luisa Gomes" draggable="false">
          </div>
          <div class="intro-content">
              <h1> Luisa Gomes </h1>
              <h2>Fotógrafa Profissional</h2>
              <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Explicabo commodi voluptate temporibus dicta qui iure consequatur ad laboriosam. Ipsa, id.</p>
              <a class="button" href="#minhas-obras">Minhas Obras</a>
          </div>
      </div>
  </main>
</template>

<script>
export default {
    name: "Intro"
}
</script>

<style lang="scss" scoped>

.intro {
    padding: 50px 0;
    animation: Intro 1.2s forwards;

    @media only screen and (max-width: 728px) {
        padding: 10px 0;
    }
}

.intro-container {
    max-width: 960px;
    margin: 0 auto;

    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    justify-content: space-between;

    @media only screen and (max-width: 728px) {
        justify-content: center !important;
        align-items: center;
    }
}

.intro-icon {
    flex: 1;
    margin-right: 32px;

     @media only screen and (max-width: 728px) {
        margin: 0 !important;
    }

    img {
        max-width: 400px;
        object-fit: cover;
        border-radius: 170px 12px;
        box-shadow: 0 0 16px rgba(0,0,0,16%);

        @media only screen and (max-width: 728px) {
            display: block;
            max-width: 400px;
            margin: 0 auto;
            object-fit: cover;
        }
    }

}

.intro-content {
    flex: 2;
    padding: 0 12px;

    @media only screen and (max-width: 728px) {
        margin-top: 20px;
    }

    h1 {
        font-size: 40px;
        font-weight: 500;
        color: #c2c2c2;

        @media only screen and (max-width: 728px) {
            font-size: 32px;
            text-align: center;
        }
    }

    h2 {
        font-size: 40px;
        font-weight: 700;
        color: #1f1f1f;

        @media only screen and (max-width: 728px) {
            font-size: 32px;
            text-align: center;
            margin-bottom: 12px;
        }
    }

    p {
        font-size: 16px;
        font-weight: 400;
        color: #c9c9c9;

        @media only screen and (max-width: 728px) {
            font-size: 14px;
            text-align: center;
        }
    }

    a.button {
        display: block;
        margin: 32px 0;
        padding: 12px;
        width: 260px;

        background: #7026F5;
        border-radius: 170px 12px;
        text-align: center;

        font-size: 22px;
        font-weight: 400;
        color: #f9f9f9;
        transition: .3s ease-in-out;

        @media only screen and (max-width: 728px) {
            text-align: center;
            margin: 18px auto;

            padding: 12px;
        }
    }

    a:hover {
        background: #7056F8;
    }
}

@keyframes Intro {
    from {
        opacity: 0;
        filter: blur(1.2px);
        transform: translate3d(0, 30px, 0);
    }
    to{
        opacity: 1;
        filter: blur(0px);
        transform: translate3d(0, 0px, 0);
    }
}

</style>
