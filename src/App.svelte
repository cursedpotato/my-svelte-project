<script>
  import FeedbackList from "./components/FeebackList.svelte";	
  let feedback = [
    {
      id: 1,
      rating: 10,
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
    },
	{
      id: 2,
      rating: 8,
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
    },
	{
      id: 3,
      rating: 7,
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
    },
  ];

  $: count = feedback.length
  $: average = feedback.reduce((a, {rating}) => a + rating, 0) / feedback.length


const deleteFeedback = (e) => {
  itemId = e.detail;
  feedback = feedback.filter((item) => item.id != item.id)
}
</script>

<main class="container">
  <h1>{average}</h1>
  <FeedbackList {feedback} on:delete-feedback={deleteFeedback}/>
</main>

<style>
</style>
