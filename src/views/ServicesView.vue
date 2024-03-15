<script>
import ViewProjectBtn from '../../src/components/ViewProjectBtn.vue'
import FAQsSection from '../../src/components/FAQsSec.vue'
import FooterComp from '../../src/components/FooterComp.vue'
export default {
  components: {
    ViewProjectBtn,
    FAQsSection,
    FooterComp
  },
  data() {
    return {
      services: {
        theService: {
          theHeader: 'PORTRAIT PHOTOGRAPHY',
          theContent:
            'Our portrait photography service is all about showcasing your unique personality. Whether you need a professional headshot, a family portrait, or a personal photoshoot. We create images that reflect your true selt. We work closely with you to bring out, your best angles and experssions, ensuring every portrait tells your story.',
          theImg: './Imgs/imageTwelve.png',
          allServices: {
            firstSession: {
              theTitle: 'Individual Session',
              thePrice: '$250',
              sessionContent: {
                one: 'IDEAL FOR CAPTURING YOUR UNIQUE PERSONALITY AND STYLE.',
                two: 'INCLUDES A 2-HOUR PHOTOSHOOT AND 20 PROFESSIONALLY EDITED IMAGES.',
                three: 'ADDITIONAL IMAGES CAN BE PURCHASED AT $10 EACH.'
              }
            },
            secondSession: {
              theTitle: 'Family Session',
              thePrice: '$400',
              sessionContent: {
                one: 'PERFECT FOR CREATING LASTING MEMORIES WITH YOUR LOVED ONES.',
                two: 'INCLUDES A 3-HOUR PHOTOSHOOT AND 30 PROFESSIONALLY EDITED IMAGES.',
                three: 'ADDITIONAL IMAGES CAN BE PURCHASED AT $10 EACH.'
              }
            },
            thirdSession: {
              theTitle: 'Couple Session',
              thePrice: '$300',
              sessionContent: {
                one: 'CELEBRATE YOUR LOVE STORY WITH AN INTIMATE PHTOSHOOT.',
                two: 'INCLUDES A 2.5-HOUR PHOTOSHOOT AND 25 PROFESSIONALLY EDITED IMAGES.',
                three: 'ADDITIONAL IMAGES CAN BE PURCHASED AT $10 EACH.'
              }
            }
          }
        },
        eventsService: {
          theHeader: 'EVENTS PHOTOGRAPHY',
          theContent:
            "Our event photography service is deditcated to capturing the magic of your special occasions. Whether it's a wedding, corporate event, or milestone celebration, We're there to document every heartfelt moment. We blend into teh background, ensuring natural and candid shots that reflect the emotions of the day.",
          theImg: './Imgs/imageThirteen.png',
          allServices: {
            firstSession: {
              theTitle: 'Wedding Photography',
              thePrice: '$1500',
              sessionContent: {
                one: 'IDEAL FOR CAPTURING YOUR UNIQUE PERSONALITY AND STYLE.',
                two: 'INCLUDES FULL-DAY PHOTOSHOOT AND 20 PROFESSIONALLY EDITED IMAGES.',
                three: 'CUSTOMIZABLE PACKAGES ARE AVAILABE TO SUIT YOUR SPECIFIC WEDDING NEEDS.'
              }
            },
            secondSession: {
              theTitle: 'Party Coverage',
              thePrice: '$800',
              sessionContent: {
                one: 'IDEAL FOR CAPTURING YOUR UNIQUE PERSONALITY AND STYLE.',
                two: 'INCLUDES FULL-DAY PHOTOSHOOT AND 20 PROFESSIONALLY EDITED IMAGES.',
                three: 'CUSTOMIZABLE PACKAGES ARE AVAILABE TO SUIT YOUR SPECIFIC WEDDING NEEDS.'
              }
            },
            thirdSession: {
              theTitle: 'Corporate Events',
              thePrice: 'Custom Pricing',
              sessionContent: {
                one: 'IDEAL FOR CAPTURING YOUR UNIQUE PERSONALITY AND STYLE.',
                two: "CONTACT US FOR A PERSONALIZED QUOTE BASED ON YOUR EVENT'S REQUIRMENTS."
              }
            }
          }
        },
        commercialService: {
          theHeader: 'COMMERCIAL PHOTOGRAPHY',
          theContent:
            "In the world of business. Whether it's a wedding, corporate event, or milestone celebration, We're there to document every heartfelt moment. We blend into teh background, ensuring natural and candid shots that reflect the emotions of the day.",
          theImg: './Imgs/imageFourteen.png',
          allServices: {
            firstSession: {
              theTitle: 'Product Photography',
              thePrice: '$500',
              sessionContent: {
                one: 'IDEAL FOR CAPTURING YOUR UNIQUE PERSONALITY AND STYLE.',
                two: 'INCLUDES FULL-DAY PHOTOSHOOT AND 20 PROFESSIONALLY EDITED IMAGES.',
                three: 'ADDITIONAL IMAGES CAN BE PURCHASED AT $20 EACH.'
              }
            },
            secondSession: {
              theTitle: 'Real Estate Coverage',
              thePrice: '$700',
              sessionContent: {
                one: 'IDEAL FOR CAPTURING YOUR UNIQUE PERSONALITY AND STYLE.',
                two: 'INCLUDES FULL-DAY PHOTOSHOOT AND 20 PROFESSIONALLY EDITED IMAGES.',
                three: 'ADDITIONAL IMAGES CAN BE PURCHASED AT $20 EACH.'
              }
            },
            thirdSession: {
              theTitle: 'Brand Photography',
              thePrice: 'Custom Pricing',
              sessionContent: {
                one: 'IDEAL FOR CAPTURING YOUR UNIQUE PERSONALITY AND STYLE.',
                two: "CONTACT US FOR A PERSONALIZED QUOTE BASED ON YOUR EVENT'S REQUIRMENTS."
              }
            }
          }
        }
      }
    }
  }
}
</script>
<template>
  <main class="flex px-12 my-8 tablet:flex-col-reverse">
    <div class="absolute left-72 tablet:relative tablet:left-0">
      <p class="text-main tracking-wide font-thin">SERVICES</p>
      <h1 class="tracking-wider font-semibold text-[2.6rem] mobile:text-[2rem]">
        DIVERSE PHOTOGRAPHY OFFERINGS
      </h1>
      <article class="text-main tracking-wide font-thin w-2/3 tablet:w-full">
        Unlock the full spectrum of professional photography services tailored to your vision. From
        timeless portraits to captivating event coverage, I bring a unique blend of creativity and
        technical expertise to each project.
      </article>
    </div>
    <div>
      <img src="./Imgs/imageSixteen.png" class="block tablet:hidden" />
      <img src="./Imgs/Image.png" class="hidden tablet:block my-6 w-full" />
    </div>
  </main>

  <span class="w-full bg-button h-[1px] block mt-10"></span>

  <section class="px-12 my-8">
    <div :key="service" v-for="service in services" class="my-20">
      <div class="flex gap-4 mb-8 tablet:flex-col-reverse">
        <div class="tracking-wider w-[60%] opacity-90 tablet:w-full">
          <h1 class="text-3xl mb-6 tracking-widest">{{ service.theHeader }}</h1>
          <article class="my-3">{{ service.theContent }}</article>
          <view-project-btn>
            <a href="#"> VIEW PROJECTS </a>
          </view-project-btn>
        </div>
        <div>
          <img :src="service.theImg" />
        </div>
      </div>

      <div>
        <div :key="theService" v-for="theService in service.allServices"
          class="grid grid-cols-2 items-center my-10 mobile:grid-cols-1">
          <div class="tracking-wider opacity-90">
            <h2 class="font-light">{{ theService.theTitle }}</h2>
            <p class="text-6xl my-2" v-html="theService.thePrice"></p>
            <ViewProjectBtn>
              <a href="tel:+000 0000000 "> BOOK A CALL </a>
            </ViewProjectBtn>
          </div>
          <div class="">
            <div :key="content" v-for="content in theService.sessionContent">
              <div class="flex items-center p-3 border-solid border-d border-[#141414] rounded-xl my-2 gap-2">
                <img src="./Icons/Clip path group.svg" class="opacity-40 w-6" />
                <p class="font-thin tracking-wider opacity-80">{{ content }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <span class="w-full bg-button h-[1px] block mt-10"></span>
    </div>
  </section>
  <FAQsSection />
  <FooterComp />
</template>
