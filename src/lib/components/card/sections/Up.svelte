<script>
  import kuroi from "$lib/assets/img/kuroi-avatar.png"
  import QuarterCircle from "$lib/etc/circularbar.svelte"
  import LinedTitle from "$lib/etc/lined_title.svelte"
  import { links } from "$lib/etc/nav_and_links.svelte"
  import { tweened } from 'svelte/motion'
  import { quadOut } from 'svelte/easing'
  
  export let intro_ended = false

  let value = tweened(0.0, {
    duration: 2000,
    easing: quadOut
  })

  $: {
    if (intro_ended){
      setTimeout(()=> {
        value.set(75.0)
        }, 300)
    }
  }

</script>

<!---------------------- Upper Section ---------------------->
<div class="flex-middle h-auto gap-2 mt-6
            max-xl:mt-4
            max-lg:flex-col max-lg:items-center">

  <!-- Arch-chan Container -->
  <div class="max-w-[16rem]
              max-xl:max-w-[13rem]
              max-lg:max-w-[12rem]
              max-sm:max-w-[10rem]">

    <!-- Arch-chan Pic Border Container (position absolute goes wank if the width and height is not redefined) -->
    <div class="absolute rounded-full
                w-[16rem] h-[16rem]
                max-xl:w-[13rem] max-xl:h-[13rem]
                max-lg:w-[12rem] max-lg:h-[12rem]
                max-sm:w-[10rem] max-sm:h-[10rem]">

      <!-- Arch-chan Pic Border Quarter Circle -->
      <div class="absolute -scale-x-100 w-full h-full">
        <section class="animate-[spin_5s]">
          <QuarterCircle bind:value={$value} info="" color="var(--theme-blue)" trackColor="transparent" thickness=4px/>
        </section>
      </div>
      <!-- Arch-chan Pic Border Dotted -->
      <div class="absolute animate-[spin_30s_linear_infinite] rounded-full w-full h-full outline-dashed outline-[--theme-blue] outline-offset-[-5px] outline-2"/>
    </div>
    <!-- Arch-chan Image -->
    <img src={kuroi} class="rounded-full scale-[90%]" alt="">
  </div>

  <!-- Biodata -->
  <div class="flex-middle flex-col gap-5 ms-10 text-center
              max-lg:mx-10 max-lg:my-8
              max-sm:text-justify">
      <!-- First Line -->
      <LinedTitle title="@kurooiii_"/>
      <!-- Introduction -->
      <div class="mx-[1rem]">
        <p1 class="font-bold">
          KUROI NARASEGAWA 『黒井奈良瀬川』
        </p1>
        <div class="flex-middle gap-4 pt-5 max-sm:flex-col max-sm:items-start">
          <p2>
            
            Original Character and Persona Combined
            <br>His name is Kuroi Narasegawa『黒井奈良瀬川』often called Kuro/Roi
            <br>He is 18 years old and have Birthday on February 1st 
            <br>He is a purple cat with fluffy tail and ears 😼
          </p2>
        </div>
      </div>
      <!-- Second Line -->
      <!-- <LinedTitle/> -->
      <!-- Links list
      <div class="flex-middle flex-row gap-2 max-sm:gap-0">

        {#each links as link}
          <a href={link.link} target="_blank" class="group hover:bg-[--theme-white] hover:glow">
            <div class="flex-middle group-hover:bg-[--theme-white]">
              <i class={link.icon + " text-3xl px-2 group-hover:text-[--theme-black]"}/>  
              <p3 class=" absolute translate-y-6 text-transparent duration-200 group-hover:text-[--theme-white]
                          group-hover:translate-y-9
                          max-sm:group-hover:translate-y-7">{link.name}</p3>
            </div>
          </a>
        {/each}

      </div> -->
  </div>
</div>