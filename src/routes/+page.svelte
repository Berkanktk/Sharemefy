<script>
    import { userData } from "$lib/firebase";
</script>

<svelte:head>
    <title>Sharemefy - a place for links</title>
    <meta name="description" content="A Social Link Sharing Platform" />
</svelte:head>

<main class="flex w-full min-h-screen">
    <div class="hero bg-base-200 flex justify-center items-start"> 
        <div class="hero-content text-center mt-32"> 
            <div class="w-full">
                <img src={`/custom.png`} alt="Icon" width="125" height="125" class="mx-auto"/>
                <h1 class="text-7xl font-bold">Sharemefy</h1>
                <p class="py-6 text-2xl">
                    One simple link to share your entire developer portfolio
                </p>
                {#if $userData?.username}
                <a href="/{$userData.username}/edit" class="btn btn-primary">Edit Profile</a>
                <a href="/{$userData.username}" class="btn btn-secondary">View Profile</a>
                {:else}
                    <a href="/login" class="btn btn-primary">Get Started</a>
                    <a href="/berkanktk" class="btn btn-secondary">Example Profile</a>
                {/if}
            </div>
        </div>
    </div>
</main>
