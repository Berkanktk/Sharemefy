<script lang="ts">
    import type { PageData } from "./$types";
    import { page } from "$app/stores";
    import { enhance } from "$app/forms";
    import { userData } from "$lib/firebase";

    export let data: PageData;
</script>

{#if $userData?.username}
<a href="/{$userData.username}/edit" class="btn btn-primary btn-md absolute right-4 top-4">Go Back</a>
{:else}
<a href="/login" class="btn btn-primary btn-md absolute right-4 top-4">Login</a>
{/if}

<main class="max-w-lg prose text-center mx-auto my-6">
    <h1 class="text-3xl font-bold">Edit Bio</h1>
    <p class="mt-4">Current Bio: <span class="text-info">{data.bio}</span></p>

    <!-- <p>Status Code: {$page.status}</p> -->
    <p class="text-error">{$page.form?.problem ?? ""}</p>

    <form class="mt-4" method="POST" use:enhance>
        <!-- Don't make a full page reload -->
        <div class="form-control">
            <label for="bio" class="label">
                <span class="label-text">Edit bio</span>
            </label>
            <textarea
                name="bio"
                class="textarea textarea-bordered textarea-accent"
                value={data.bio}
            />
        </div>
        <button class="btn btn-primary my-5">Update Bio</button>
    </form>
</main>
