<template>
  <div class="academic">
      <div class="academic-container">
          <div class="academic-logo">
              <img src="@/assets/LuisaGomes.jpeg" alt="Luisa Gomes">
          </div>
          <div class="academic-content">
              <div class="line-1">
                  <span> 2009 - 2021 </span>
                  <p>Instituto de Educação Isabella Clyaton</p>
              </div>
              <div class="line-2">
                  <span> 2022 - 2021 </span>
                  <p>PUC Minas - Artes Visuais</p>
              </div>
              <div class="line-3">
                  <span> 2022 - 2021 </span>
                  <p>UFMG - Pós Graduação em Artes Visuais</p>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "Academic"
}
</script>

<style scoped lang="scss">
    .academic {
        padding: 50px 0;
    }

    .academic-container {
        max-width: 960px;
        margin: 12px auto;

        display: flex;
        align-items: flex-start;
        align-content: center;
        flex-wrap: wrap;
        justify-content: space-between;
    }

    .academic-logo {
        flex: 1;
        margin-right: 50px;

        img {
            display: block;
            width: 300px;
            height: 300px;
            object-fit: cover;
            border-radius: 100%;
        }

    }

    .academic-content {
        flex: 2;

        .line-1 {
            margin: 22px 0;
            position: relative;
            max-width: 100%;
            padding: 20px;

            box-shadow: 2px 2px 16px rgba(0,0,0,16%);
            border-radius: 12px;

            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;

            span {
                display: block;
                position: absolute;

                left: -30px;

                background: #7026F5;
                width: 150px;
                padding: 4px;

                border-radius: 150px 12px;
                color: #E6E0F2;

                font-weight: 400;
            }

            p {
                margin-left: 40px;
                color: #1f1f1f;
                font-size: 18px;
                font-weight: 400;
            }
        }

        .line-2 {
            margin: 22px 0;
            position: relative;
            max-width: 100%;
            padding: 20px;

            box-shadow: 2px 2px 16px rgba(0,0,0,16%);
            background: #E6E0F2;
            border-radius: 12px;

            span {
                display: block;
                position: absolute;

                left: -30px;

                background: #7026F5;
                text-align: center;
                width: 150px;
                padding: 4px;

                border-radius: 150px 12px;
                color: #E6E0F2;

                font-weight: 400;
            }

            p {
                margin-left: 130px;
                color: #1f1f1f;
                font-size: 18px;
                font-weight: 400;
            }
        }

        .line-3 {
            margin: 22px 0;
            position: relative;
            max-width: 100%;
            padding: 20px;

            box-shadow: 2px 2px 16px rgba(0,0,0,16%);
            background: #333333;
            border-radius: 12px;

            span {
                display: block;
                position: absolute;

                left: -30px;

                background: #7026F5;
                text-align: center;
                width: 150px;
                padding: 4px;

                border-radius: 150px 12px;
                color: #E6E0F2;

                font-weight: 400;
            }


            p {
                margin-left: 130px;
                color: #fff;
                font-size: 18px;
                font-weight: 400;
            }
        }
    }
</style>
