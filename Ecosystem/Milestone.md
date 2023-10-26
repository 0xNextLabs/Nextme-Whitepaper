# Milestone

## Nextme's Ecosystem

> Every move, every path, is interconnected.

<article class='py-4'>
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
        class='relative h-full text-sm text-white flex flex-col items-center'
      >
        <h3 class='!text-white'>{{row?.title}}</h3>
        <span>{{row?.time}}</span>
        <p class='px-4 leading-4'>{{row?.desc?.data}}</p>
        <a :href="row?.url" target='_blank' class='absolute bottom-4'>
          <button 
            :class="['rounded-md text-white border-white w-36 py-3 backdrop-blur-sm',row?.released ? 'rounded-3xl bg-zinc-950/10' : 'bg-stone-100/30']"
            :disabled="!row?.released"
          >{{row?.label}}
          </button>
        </a>
      </div>
    </li>
  </ul>
</article>
