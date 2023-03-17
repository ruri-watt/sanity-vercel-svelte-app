<script lang='ts'>
  import type {Day} from '$lib/types'

  export let days: Day[]
</script>

{#each days as day}
  <div class='card'>
    <h3>{day.date}</h3>
    <p>{day.description}</p>
    {#if day.talks.length}<h3>Talks</h3> {/if}
    {#each day.talks as talk}
      <div class='card'>
        <h4>{talk.title}</h4>
        <p>{talk.time}</p>
        <p>{talk.speaker.name}</p>
        <img class='speaker-image' src='{talk.speaker.imageUrl}' alt='{talk.speaker.imageUrl}'>
      </div>
    {/each}

    {#if day.talks.length}<h3>Speakers</h3>{/if}
    {#each day.speakers as speaker}
      <div class='card'>
      <p>{speaker.name}</p>
      <img class='speaker-image' src='{speaker.imageUrl}' alt='{speaker.imageUrl}'>
      </div>
    {/each}
  </div>
{/each}

<style>
    .card {
        border: 1px solid black;
        margin: 10px;
    }

    .speaker-image {
        border-radius: 10px;
        width: 40px;
    }
</style>