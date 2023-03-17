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
        <p>When? {talk.time.split('T')[1].slice(0, 5)}</p>
        <p>Who? {talk.speaker.name}</p>
        <img class='speaker-image' src='{talk.speaker.imageUrl}' alt='{talk.speaker.imageUrl}'>
      </div>
    {/each}

    {#if day.speakers.length}<h3>Speakers</h3>
      <div class='card'>
        {#each day.speakers as speaker}
          <div class='speaker-span'>
            <img class='speaker-image' src='{speaker.imageUrl}' alt='{speaker.imageUrl}'>
            <div>{speaker.name}</div>
          </div>
        {/each}
      </div>
    {/if}
  </div>
{/each}

<style>
    .card {
        border: 1px solid black;
        border-radius: 5px;
        margin: 10px;
        padding: 10px;
        background-color: #f1f3f6;
    }

    .speaker-image {
        border-radius: 10px;
        max-width: 60px;
        max-height: 60px
    }

    .speaker-span {
        display: inline-block;
        margin-right: 20px;
        margin-bottom: 0;
    }
</style>