<script>
  import { Swiper, SwiperSlide } from "swiper/svelte";
  import { Autoplay, Pagination, Navigation } from "swiper";

  import "swiper/css";
  import "swiper/css/navigation";
  import "swiper/css/pagination";

  const items = [
    {
      name: "Leonardo",
      age: 26,
      location: "Italy"
    },
    {
      name: "Maria",
      age: 27,
      location: "Brazil"
    },
    {
      name: "Oliver",
      age: 28,
      location: "United States"
    },
    {
      name: "Margarida",
      age: 29,
      location: "Portugal"
    }
  ];
</script>

<Swiper 
  loop={true}
	spaceBetween={30}
	slidesPerView={2}
	autoplay={{
		delay: 1000,
		disableOnInteraction: false
	}}
	navigation={true}
  modules={[Autoplay, Navigation, Pagination]}
>
  {#each items as item, i}
    <SwiperSlide>
      <div class="item">
        <strong>{item.name}</strong> ({item.age})
        from {item.location}
      </div>
    </SwiperSlide>
  {/each}
</Swiper>

<style>
  .item {
    font-family: sans-serif;
    padding: 30px 8px;
    text-align: center;
    background: rgb(237, 234, 243);
    border-radius: 5px;
  }
</style>