<script>
import ViewProjectBtn from '../../src/components/ViewProjectBtn.vue'
import FAQsSec from '../../src/components/FAQsSec.vue'
import FooterComp from '../../src/components/FooterComp.vue'
export default {
  data() {
    return {
      projects: {
        portraitProjects: {
          header: "PORTRAIT'S PHOTOGRAPHY",
          projectItems: {
            project1: {
              img: './Imgs/imageSix.png',
              caption: 'Faces Of Resilience',
              date: 'March 2022'
            },
            project2: {
              img: './Imgs/imageFour.png',
              caption: 'Innocence Unveiled',
              date: 'January 2020'
            },
            project3: {
              img: './Imgs/imageFive.png',
              caption: 'Elegance in Monochrom',
              date: 'March 2021'
            }
          }
        },
        eventProjects: {
          header: 'EVENTS PHOTOGRAPHY',
          projectItems: {
            project1: {
              img: './Imgs/imageFifteen.png',
              caption: 'A Wedding Tale',
              date: 'September 2021'
            },
            project2: {
              img: './Imgs/imageSeven.png',
              caption: 'Corporate Excellence Summit',
              date: 'November 2019'
            },
            project3: {
              img: './Imgs/imageEight.png',
              caption: 'Festival Of Colors',
              date: 'March 2018'
            }
          }
        },
        commercialProjects: {
          header: 'COMMERCIAL PHOTOGRAPHY',
          projectItems: {
            project1: {
              img: './Imgs/imageNine.png',
              caption: 'Product Elegance',
              date: 'August 2020'
            },
            project2: {
              img: './Imgs/imageTen.png',
              caption: 'Brand Storytelling',
              date: 'May 2019'
            },
            project3: {
              img: './Imgs/imageEleven.png',
              caption: 'Culinary Delights',
              date: 'April 2017'
            }
          }
        }
      },
      imgs: [
        '/Imgs/Logo.png',
        '/Imgs/logoOne.png',
        '/Imgs/logoTwo.png',
        '/Imgs/logoThree.png',
        '/Imgs/logoFour.png',
        '/Imgs/Logo.png',
        '/Imgs/logoOne.png',
        '/Imgs/logoTwo.png',
        '/Imgs/logoThree.png',
        '/Imgs/logoFour.png'
      ]
    }
  },
  components: {
    ViewProjectBtn,
    FAQsSec,
    FooterComp
  }
}
</script>

<template>
  <main class="flex flex-col p-12 relative tablet:flex-col-reverse">
    <div class="absolute tablet:relative">
      <p class="text-main tracking-wide font-thin">PORTFOLIO</p>
      <h1 class="tracking-wider font-semibold text-[2.6rem] mobile:text-[2rem]">
        VISUAL POETRY IN PIXELS
      </h1>
      <article class="text-main tracking-wide font-thin w-2/3 tablet:w-full">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nihil placeat ipsa voluptate magni
        reprehenderit reiciendis quibusdam totam adipisci ex. Voluptatibus esse natus adipisci
        debitis velit quae, saepe quam. Odit, aperiam. Lorem ipsum dolor sit, amet consectetur
        adipisicing elit. Quibusdam beatae optio praesentium ut, quos voluptas ipsum obcaecati enim
        aliquam perspiciatis, iure, harum fugiat aliquid fuga dolores ad ipsa natus excepturi?
      </article>
    </div>
    <div>
      <img src="./Imgs/Portfolio-Des.png" class="block tablet:hidden" />
      <img src="./Imgs/Portfolio-Mob.png" class="hidden tablet:block my-6 w-full" />
    </div>
  </main>
  <div class="py-10">
    <h2 class="text-main text-center font-light tracking-wider mb-4">BRANDS I HAVE WORKED WITH</h2>
    <div class="flex bg-button overflow-hidden">
      <div class="inline-flex animate-slide">
        <div :key="img" v-for="img in imgs">
          <img :src="img" class="max-w-fit" />
        </div>
      </div>
    </div>
  </div>
  <section class="p-12">
    <div :key="project" v-for="project in projects">
      <h1 class="text-main tracking-wide font-semibold text-3xl my-4">{{ project.header }}</h1>
      <div class="flex items-center gap-4 my-4 mobile:grid">
        <div :key="theDetails" v-for="theDetails in project.projectItems">
          <img :src="theDetails.img" :alt="theDetails.caption" class="cursor-pointer" />
          <div class="flex justify-between items-baseline">
            <h2 class="text-[#d3d3d3] tracking-wider text-xl mt-2">{{ theDetails.caption }}</h2>
            <view-project-btn>
              <router-link to="/testcomponent">VIEW PROJECT</router-link>
            </view-project-btn>
          </div>
          <span class="text-main tracking-wide"> {{ theDetails.date }} </span>
        </div>
      </div>
      <span class="w-full bg-button h-[1px] block mt-10"></span>
    </div>
  </section>
  <FAQsSec />
  <FooterComp />
</template>
