<script>
  import {FeedbackStore} from '../stores';
  import Card from './Card.svelte';

  export let item;

  const handleDelete = (itemId) => {
    FeedbackStore.update((currentFeedback) => {
      return currentFeedback.filter(item => item.id !== itemId);
    });
  }
</script>

<Card>
  <button class="num-display">
    {item.rating}
  </button>
  <div class="close" on:click={() => handleDelete(item.id)}>X</div>
  <p class="text-display">
    {item.text}
  </p>
</Card>

<style>
  .num-display {
    position: absolute;
    top: -1rem;
    left: -1rem;
    width: 5rem;
    height: 5rem;
    background: #ff6a95;
    color: #fff;
    border: 1px solid #eee;
    border-radius: 50%;
    padding: 1rem;
    text-align: center;
    font-size: 1.9rem;
  }

  .close {
    position: absolute;
    top: 1rem;
    right: 1rem;
    cursor: pointer;
    background: none;
    border: none;
  }
</style>