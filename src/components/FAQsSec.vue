<template>
  <section class="px-12">
    <div>
      <p class="text-main tracking-wider font-thin">FAQ'S</p>
      <h1 class="tracking-wide font-semibold text-3xl">FREQUENTLY ASKED QUESTIONS</h1>
    </div>
    <div class="grid gap-7 grid-cols-2 my-10 mobile:grid-cols-1">
      <div :key="faq" v-for="faq in faqs">
        <div class="flex gap-3 justify-between">
          <h2 class="text-[#d3d3d3] text-xl tracking-wide">{{ faq.question }}</h2>
          <div>
            <GetIn @click="faq.isBlind = !faq.isBlind" :class="{ hidden: faq.isBlind }" class="cursor-pointer" />
            <GetOut @click="faq.isBlind = !faq.isBlind" class="cursor-pointer" :class="{ hidden: !faq.isBlind }" />
          </div>
        </div>
        <p class="text-main my-3 tracking-wide font-thin" v-show="faq.isBlind">{{ faq.answer }}</p>
      </div>
    </div>
    <div></div>
  </section>
</template>

<script>
import GetIn from '../../src/components/IconsSVGs/GetInIcon.vue'
import GetOut from '../../src/components/IconsSVGs/GetOutIcon.vue'

export default {
  data() {
    return {
      faqs: {
        faq1: {
          question: 'WHAT TYPE OF PHOTOGRAPHY DO YOU SPECIALIZE IN ?',
          answer:
            'I specialize in [ Portrait, LandScape, Event, etc.. & photography, capturing moments that tell unique stories]',
          isBlind: false
        },
        faq2: {
          question: 'HOW CAN I BOOK A PHOTOGRAPHY SESSION WITH YOU ?',
          answer:
            'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque iure totam praesentium',
          isBlind: false
        },
        faq3: {
          question: 'WHAT EQUIPMENT DO YOU USE FOR YOUR PHOTOGRAPHY ?',
          answer:
            'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque iure totam praesentium',
          isBlind: false
        },
        faq4: {
          question: 'CAN I REQUEST A SPECIFIC LOCATION FOR A SESSION ?',
          answer:
            'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque iure totam praesentium',
          isBlind: false
        },
        faq5: {
          question: 'WHAT IS YOUR EDITING PROCESS LIKE ?',
          answer:
            'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque iure totam praesentium',
          isBlind: false
        },
        faq6: {
          question: 'ARE DIGITAL FILES INCLUDED IN YOUR PHOTOGRAPHY PACKAGES ?',
          answer:
            'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque iure totam praesentium',
          isBlind: false
        }
      },
      GetInIcon: GetIn,
      GetOutIcon: GetOut
    }
  },
  components: {
    GetIn,
    GetOut
  }
}
</script>
