<script lang="ts">
  import UserLink from "$lib/components/UserLink.svelte";
  import type { PageData } from "./$types";
  import { userData } from "$lib/firebase";

  export let data: PageData;
</script>

<svelte:head>
  <title>@{data.username} Links</title>
  <meta name="description" content={data.bio} />
</svelte:head>

<main class="prose text-center mx-auto mt-2">

  {#if $userData?.username === data.username}
    <a href="{data.username}/edit" class="btn btn-primary btn-md absolute right-4 top-4">Edit Profile</a>
  {/if}

  <img
    src={data.photoURL ?? "/user.png"}
    alt="photoURL"
    width="256"
    height="256"
    class="mx-auto mt-8 rounded-full w-64 h-64 object-cover"
  />

  <h1 class="text-5xl text-purple-500 font-bold mt-5">
    @{data.username}
  </h1>

  <p class="mt-1">Joined {data.createdAt}</p>

  <p class="text-xl mb-8 mt-4">{data.bio ?? "No bio yet..."}</p>
  <ul class="list-none">
    {#each data.links as item}
      <li class="my-4">
        <UserLink {...item} />
      </li>
    {/each}
  </ul>

  {#if $userData?.username === data.username}
    <a href={data.username+"/edit"} class="stack w-full max-w-md text-center bg-base-200 flex justify-center items-center p-4 rounded-lg not-prose no-underline">
      <span class="text-lg text-white font-bold">+ Add New</span>
    </a>
  {/if}
</main>
