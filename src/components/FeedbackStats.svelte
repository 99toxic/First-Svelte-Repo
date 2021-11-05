<script>
  import {FeedbackStore} from '../stores';

  $: count = $FeedbackStore.length;
	$: average = $FeedbackStore.reduce((acc, cur) => acc + cur.rating, 0) / count;
</script>

<div class="feedback-statss">
  <h4>{count} Reviews</h4>
  <h4>Ratings Average: {average}</h4>
</div>

<style>
  .feedback-statss {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>