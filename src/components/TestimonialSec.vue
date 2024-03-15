<script>
import ForButtons from '../../src/components/ForButtons.vue'
import ArrowLeft from '../../src/components/IconsSVGs/ArrowLeft.vue'
import ArrowRight from '../../src/components/IconsSVGs/ArrowRight.vue'
import FacebookSVG from '../../src/components/IconsSVGs/FacebookSVG.vue'
import InstaSVG from '../../src/components/IconsSVGs/InstaSVG.vue'
import YoutubeSVG from '../../src/components/IconsSVGs/YoutubeSVG.vue'
export default {
  components: {
    ForButtons,
    ArrowLeft,
    ArrowRight,
    FacebookSVG,
    InstaSVG,
    YoutubeSVG
  },
  data() {
    return {
      testimonials: {
        test1: {
          userName: 'Emily Johnson',
          userAddress: 'USA,California',
          userFacebook: 'userFacebookLink',
          userInstagram: 'userInstagramLink',
          userYoutube: 'userYoutubeChannelLink',
          userComment:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem omnis, doloremque accusamus nemo dolore quo ipsum praesentium '
        },
        test2: {
          userName: 'John Smith',
          userAddress: 'France,Paris',
          userFacebook: 'userFacebookLink',
          userInstagram: 'userInstagramLink',
          userYoutube: 'userYoutubeChannelLink',
          userComment:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem omnis, doloremque accusamus nemo dolore quo ipsum praesentium '
        },
        test3: {
          userName: 'Samantha Davis',
          userAddress: 'Germany,Berlin',
          userFacebook: 'userFacebookLink',
          userInstagram: 'userInstagramLink',
          userYoutube: 'userYoutubeChannelLink',
          userComment:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem omnis, doloremque accusamus nemo dolore quo ipsum praesentium '
        }
      },
      reviews: '323'
    }
  }
}
</script>

<template>
  <section class="p-12 mt-10 mobile:p-8">
    <div class="flex justify-between tablet:flex-col">
      <div>
        <p class="text-main tracking-wide font-thin">TESTIMONIALS</p>
        <h1 class="tracking-wider font-semibold text-4xl">WHAT MY CLIENTS SAY</h1>
        <h2 class="mt-7 opacity-40 tracking-wider font-light">Total Reviews</h2>
        <p class="text-xl">{{ reviews }} View</p>
      </div>
      <div class="inline-flex items-center gap-2 mt-6 tablet:self-end">
        <ArrowLeft class="w-8 cursor-pointer" />
        <ArrowRight class="w-8 cursor-pointer" />
        <ForButtons class="px-3 rounded">View All Testimonials</ForButtons>
      </div>
    </div>
    <main class="flex justify-between gap-8 my-8 tablet:flex-col">
      <div :key="testimonial" v-for="testimonial in testimonials" class="p-6 bg-[#141414] rounded">
        <div class="flex items-center justify-between gap-10">
          <div>
            <h3>{{ testimonial.userName }}</h3>
            <p class="opacity-30 font-light tracking-wide text-sm">{{ testimonial.userAddress }}</p>
          </div>
          <div class="flex gap-2 bg-black rounded-full p-1">
            <FacebookSVG>
              <a :href="testimonial.userFacebook"></a>
            </FacebookSVG>
            <InstaSVG>
              <a :href="testimonial.userInstagram"></a>
            </InstaSVG>
            <YoutubeSVG>
              <a :href="testimonial.userYoutube"></a>
            </YoutubeSVG>
          </div>
        </div>
        <div class="my-4">
          <p class="text-yellow-500">stars</p>
        </div>
        <div>
          <p>{{ testimonial.userComment }}</p>
        </div>
      </div>
    </main>
  </section>
</template>
