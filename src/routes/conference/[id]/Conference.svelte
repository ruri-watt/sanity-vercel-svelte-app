<script lang='ts'>
  import type {Conference} from '$lib/types'

  export let conference: Conference
</script>

<div>
  <h1>{conference.title}</h1>
  <p>{conference.description}</p>
  <p>Where? {conference.location}</p>
</div>

<style></style>