<script>
  export let meetups;

  import MeetupItem from "./MeetupItem.svelte";
</script>

<section id="meetups">
  {#each meetups as meetup (meetup.id)}
    <MeetupItem {...meetup} />
  {/each}
</section>

<style>
  section {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 1;
  }

  @media (min-width: 768px) {
    section {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>
