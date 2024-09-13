<script lang="ts">
    import { onMount } from "svelte";

    let christmasDate = new Date('2024-12-24T00:00:00').getTime();
    let now = new Date().getTime();
    let differenceBetweenDate = christmasDate - now;
    let days: number;
    let hours: number;
    let minutes: number;
    let seconds: number;
    let interval: number;
    
    const updateTime = () => {
        differenceBetweenDate = christmasDate - now;
    }

    onMount(() => {
        interval = setInterval(() => { updateTime() }, 1000);

        return () =>  {
            clearInterval(interval);
        }
    })

   $: days = Math.floor(differenceBetweenDate / (1000 * 60 * 60 * 24));
   $: hours = Math.floor((differenceBetweenDate % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
   $: minutes = Math.floor((differenceBetweenDate % (1000 * 60 * 60)) / (1000 * 60));
   $: seconds = Math.floor((differenceBetweenDate % (1000 * 60)) / 1000);

</script>

<main>
<p>
    {days} dager og {hours} timer : {minutes} minutter : {seconds} sekunder
</p>
<p> Det er {days} dager til 🌲🎅🏻 </p>
</main>

<style>
    main {
    margin-top: 100px;
    margin-bottom: 70px;
    padding: 1rem;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
    text-align: center;
  }
</style>