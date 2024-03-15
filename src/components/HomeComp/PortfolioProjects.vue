<template>
  <section class="px-12">
    <div class="flex justify-between items-end my-10 mobile:grid">
      <div>
        <p class="text-main tracking-wider font-thin">PORTFOLIO</p>
        <h1 class="tracking-wide font-semibold text-3xl">EXPLORE MY PHOTOGRAPHY WORK.</h1>
      </div>
      <div class="inline-flex gap-4 mobile:grid my-6">
        <div class="flex gap-2">
          <ArrowLeft class="cursor-pointer" />
          <ArrowRight class="cursor-pointer" />
        </div>
        <ForButtons class="w-36 rounded-lg">
          <a href="#">View All Services</a>
        </ForButtons>
      </div>
    </div>
    <div class="flex gap-4 items-center mobile:grid">
      <div :key="item" v-for="item in items">
        <img :src="item.source" class="cursor-pointer" />
        <div class="flex justify-between items-start py-2">
          <div>
            <h2 class="text-[#d3d3d3] tracking-wider text-xl">{{ item.title }}</h2>
            <span class="text-main tracking-wide">{{ item.date }} </span>
          </div>
          <ViewProjectBtn>
            <RouterLink to="/testcomponent">VIEW PROJECT</RouterLink>
          </ViewProjectBtn>
        </div>
      </div>
    </div>
  </section>
  <RouterView />
</template>

<script>
import ArrowLeft from '../../../src/components/IconsSVGs/ArrowLeft.vue'
import ArrowRight from '../../../src/components/IconsSVGs/ArrowRight.vue'
import ForButtons from '../../../src/components/ForButtons.vue'
import ViewProjectBtn from '../../../src/components/ViewProjectBtn.vue'
import { RouterLink, RouterView } from 'vue-router'

export default {
  components: {
    ForButtons,
    ArrowRight,
    ArrowLeft,
    ViewProjectBtn,
    RouterLink,
    RouterView
  },
  data() {
    return {
      items: {
        itemOne: {
          title: 'Faces Of Resilience',
          date: 'March 2022',
          source: './Imgs/projectOne.png'
        },
        itemTwo: {
          title: 'A Wedding Tale',
          date: 'January 2021',
          source: './Imgs/projectTwo.png'
        },
        itemThree: {
          title: 'Product Elegance',
          date: 'May 2020',
          source: './Imgs/projectThree.png'
        }
      }
    }
  }
}
</script>
