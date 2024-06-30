<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";

  const meetups = [
    {
      id: "m1",
      title: "Coding Bootcamp",
      subtitle: "Learn to code",
      description: "Learn to code",
      imageUrl:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/6/67/London_Skyline_%28125508655%29.jpeg/640px-London_Skyline_%28125508655%29.jpeg",
      address: "27th Nerd Road, 32523 New York",
      contactEmail: "code@test.com",
    },
    {
      id: "m2",
      title: "Swimming Course",
      subtitle: "Learn to swim",
      description: "Learn swimming techniques",
      imageUrl:
        "https://cdn.britannica.com/08/136908-050-9F238126/Thames-River-London-England.jpg",
      address: "123 Pool Lane, City",
      contactEmail: "swim@example.com",
    },
  ];
</script>

<Header />
<main>
  <MeetupGrid {meetups} />
</main>

<style>
</style>
