<script>
export default {
  data() {
    return {
      journeys: {
        jour1: {
          year: '2005',
          story:
            'In 2005, Damien acquired her first camera, igniting her passion for photography.<br>She started experimenting with landscapes and candid shots, marking the beginning of her visual storyteling journey.'
        },
        jour2: {
          year: '2010',
          story:
            'Damien pursed a degree in Fine Arts with a focus on photography, refining her<br>technical skills and artistic sensibilities.'
        },
        jour3: {
          year: '2012',
          story:
            'In 2012, Damien held her first solo exhibition, showcasing her unique perspective<br>on nature and people through her lens.'
        },
        jour4: {
          year: '2015',
          story:
            'Damien officially launched her photography business in 2015, offering portrait,<br>event and commercial photography services.'
        },
        jour5: {
          year: '2017',
          story:
            "Damien's work took her beyond the USA, capturing breathtaking scenes and<br>cultures from around the world."
        },
        jour6: {
          year: '2020',
          story:
            "In 2020, Damien's dedication and creativity earned her several prestigious photography awards, solidifying her position as a visionary photographer."
        }
      }
    }
  }
}
</script>

<template>
  <section class="p-12">
    <div>
      <p class="text-main tracking-wide font-thin">JOURNEY</p>
      <h1 class="tracking-wider font-semibold text-4xl">DAMIEN'S JOURNEY - A TIMELINE</h1>
    </div>
    <div class="grid grid-cols-2 grid-rows-3 gap-6 mt-10 mobile:grid-cols-1">
      <div :key="journey" v-for="journey in journeys" class="bg-[#141414] p-6 rounded">
        <h2 class="opacity-40 tracking-wider text-3xl mb-3 font-semibold">
          YEAR - {{ journey.year }}
        </h2>
        <blockquote v-html="journey.story" class="opacity-40 tracking-wide"></blockquote>
      </div>
    </div>
  </section>
</template>
