<template>
  <section class="my-jobs" id="minhas-obras">
      <h1>
          <span> Minhas </span> Obras
      </h1>
      <div class="my-jobs-container">
          <div class="job" v-for="(job) of jobs" :key="job.id">
              <div class="job-icon">
                  <img :src="job.source" :alt="job.title" draggable="false" />
              </div>
              <div class="job-content">
                  <h2> {{job.title}} </h2>
                  <p>{{ job.description }}</p>
                  <a href="#"> Ver Mais </a>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
import { reactive, ref, toRefs } from 'vue'
import iconBeach from "@/assets/icons/beaches.svg";
import iconCat from "@/assets/icons/cat-icon.svg";
import iconSchool from "@/assets/icons/school-icons.svg";

export default {
    name: "MyJob",
    setup(){
        const data = reactive({
            jobs: [
                {
                    id: Math.random(),
                    title: "Praias & Montanhas",
                    description: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quaerat corporis suscipit esse.",
                    source: iconBeach
                },
                {
                    id: Math.random(),
                    title: "Animais",
                    description: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quaerat corporis suscipit esse.",
                    source: iconCat
                },
                {
                    id: Math.random(),
                    title: "Formatura",
                    description: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quaerat corporis suscipit esse.",
                    source: iconSchool
                },
            ],
        });
        const value = ref(0);

        return {
            ...toRefs(data),
            value
        }
    }
}
</script>

<style scoped lang="scss">
    .my-jobs {
        margin-top: 50px;
        padding: 50px 0;

        > h1 {
            padding-left: 15px;
            max-width: 960px;
            margin: 0 auto;

            font-size: 50px;
            font-weight: 700;
            color: #d9d9d9;
            text-transform: uppercase;
            letter-spacing: 1.175px;

            span {
                font-weight: 300;
                text-transform: uppercase;
                letter-spacing: 1.175px;
            }
        }
    }

    .my-jobs-container {
        max-width: 960px;
        margin: 20px auto;

        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        align-items: flex-start;
        align-content: center;
    }

    .job {
        width: 300px;
        margin: 0 auto;

        box-shadow: 1px 1px 16px rgba(0,0,0,16%);
        text-align: center;

        border-radius: 12px;
        padding: 16px 0;
        cursor: pointer;
        transform: translate3d(0px, 0px, 0);
        transition: .3s ease-in-out;

        .job-icon {
            max-width: 100%;
            display: flex;
            justify-content: center;
        }

        img {
            display: block;
            max-width: 100%;
            height: 120px;
            margin: 12px 0 0 0;
        }

        h2 {
            margin-top: 32px;
            font-weight: 300;
            font-size: 24px;
            text-align: center;
        }

        p {
            margin-top: 8px;
            padding: 0 12px;
            font-size: 13px;
            color: #c2c2c2;
        }

        a {
            display: block;
            margin: 12px auto;
            padding: 8px;
            width: 220px;

            background: #7026F5;
            border-radius: 170px 12px;
            text-align: center;

            font-size: 18px;
            font-weight: 400;
            color: #f9f9f9;
            transition: .3s ease-in-out;
        }

        a:hover {
            background: #7056F8;
        }
    }

    .job:hover {
        transform: translate3d(0px, -10px, 0);
    }
</style>
