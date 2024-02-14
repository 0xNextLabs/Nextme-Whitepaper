# Milestone

## Nextme's Ecosystem

> Every move, every path, is interconnected.

<article class='py-4 max-sm:pb-12'>
  <ul class="flex flex-wrap justify-center gap-8 !pl-0">
    <li 
      v-for="(row,index) in milestone.cardsData" :key="`card-${index}`"
      class="w-full sm:w-72 h-[28rem] sm:animate__animated animate__fadeInRight transition-all rounded-2xl relative shadow-sm overflow-hidden"
      :style="{
        animationDelay: `${index * 0.5}s`,
      }"
    >
      <div 
        class='absolute w-full h-full' 
        :style="{ backgroundColor: row?.color }"
      >
        <image v-if="row?.image" alt="" :src="`${cdn}/${row?.image}`" class="object-cover w-full h-full" />
      </div>
      <section
        class='relative h-full text-base sm:text-sm text-white flex flex-col items-center'
      >
        <header v-if='row?.released && index !== 3' class="absolute right-2.5 top-2.5 flex h-3 w-3">
          <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-gray-50 opacity-75"></span>
          <span class="relative inline-flex rounded-full h-3 w-3 bg-gray-100"></span>
        </header>
        <h3 class='!text-white'>{{ `${config.title} ${row?.title}`}}</h3>
        <span>{{row?.time}}</span>
        <p class='px-4 leading-4'>{{row?.desc?.data}}</p>
        <a :href="row?.url" target='_blank' class='absolute bottom-4'>
          <button 
            :class="['rounded-md text-white border-white w-40 sm:w-36 py-3 backdrop-blur-sm',row?.released ? 'rounded-3xl bg-zinc-950/10' : 'bg-stone-100/30']"
            :disabled="!row?.released"
          >{{row?.label}}
          </button>
        </a>
      </div>
    </li>
  </ul>
</article>
