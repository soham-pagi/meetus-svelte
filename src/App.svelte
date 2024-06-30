<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import TextInput from "./UI/TextInput.svelte";

  let title = "";
  let subtitle = "";
  let description = "";
  let imageUrl = "";
  let address = "";
  let contactEmail = "";

  let meetups = [
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

  function addMeetup() {
    const newMeetup = {
      id: Math.random().toString(),
      title,
      subtitle,
      description,
      imageUrl,
      address,
      contactEmail,
    };

    meetups = [...meetups, newMeetup];
  }
</script>

<Header />
<div style="margin-top: 5rem"></div>

<main>
  <form on:submit|preventDefault={addMeetup}>
    <TextInput
      id="title"
      label="Title"
      value={title}
      on:input={(event) => (title = event.target.value)}
    />
    <TextInput
      id="subtitle"
      label="Subtitle"
      value={subtitle}
      on:input={(event) => (subtitle = event.target.value)}
    />
    <TextInput
      id="address"
      label="Address"
      value={address}
      on:input={(event) => (address = event.target.value)}
    />
    <TextInput
      id="imageUrl"
      label="Image Url"
      value={imageUrl}
      on:input={(event) => (imageUrl = event.target.value)}
    />
    <TextInput
      id="email"
      label="E-mail"
      value={contactEmail}
      on:input={(event) => (contactEmail = event.target.value)}
    />

    <TextInput
      id="description"
      rows="3"
      label="Description"
      controlType="textarea"
      value={description}
    />

    <button type="submit">Save</button>
  </form>

  <MeetupGrid {meetups} />
</main>

<style>
</style>
