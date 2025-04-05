<script>
  import saken from "$lib/assets/img/fav-kuro.png"
  export var color
  export var path
  export var icon
  export var show_rounded_line = false

  if (path == null) path = "kurooii"
  if (icon == null) icon = "fa-solid fa-house"
  if (color == null) color = "text-[--theme-absolute-white]"

</script>
<div class="flex-middle items-start">
  <!-- Wanky Rounded Left -->
  {#if show_rounded_line}
    <div class="corner-border-l-nord translate-x-5 translate-y-[9px] rounded-tl-xl"/>
    <div class="border-l-only translate-x-5 translate-y-[28px]"/>
    <div class="corner-border-l-nord translate-x-5 translate-y-[48px] -scale-y-100 rounded-tl-xl"/>
  {/if}
  <!-- Line Section -->
  <div class="flex-middle">
    <!-- Start -->
    <div class="flex flex-row text-[--theme-cyan]">
      <div class="bg-[--theme-nord] pl-3 pr-5 flex-middle">
        <!-- <i class={"fa-brands fa-linux text-[--theme-absolute-white] mr-5"}/> -->
        <img src={saken} class="scale-[85%]" alt="">
        <p2 class={color + " mx-0 font-bold"}>{path}</p2>
      </div>
      <div class="border-t-[15px] border-b-[15px] border-t-transparent border-l-[15px] border-l-[--theme-nord] border-b-transparent
                  max-sm:border-t-[8px] max-sm:border-b-[8px]"/>
    </div>
    <!-- Line -->
    <div class="h-[2px] w-full bg-[--theme-nord]"/>
    <!-- End -->
    <div class="flex flex-row text-black">
      <div class="border-t-[15px] border-b-[15px] border-t-transparent border-r-[15px] border-r-[--theme-nord] border-b-transparent
                  max-sm:border-t-[8px] max-sm:border-b-[8px]"/>
      <div class="bg-[--theme-nord] pr-3 pl-5 flex-middle">
        <p2 class={color + " mx-0 font-bold"}>{path}</p2>
        <img src={saken} class="scale-[85%]" alt="">
      </div>
    </div>  
  </div>
</div>