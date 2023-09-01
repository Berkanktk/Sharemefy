<script>
    export let id = Date.now().toString();
    export let icon = 'default';
    export let url = 'foo';
    export let title = 'some cool title';
</script>

<a id={id} href={url} class="stack w-full max-w-md text-center bg-base-300 flex justify-center items-center p-4 rounded-lg not-prose no-underline" target="_blank">
  <img src={`/${icon}.png`} alt={icon} width="32" height="32" class="w-8" />
  <span class="text-lg text-white font-bold">{title}</span>
</a>

<style>
    .stack {
        height: 64px;
        transition: transform 0.3s ease;
    }

    .stack:hover {
        transform: scale(1.05);
    }

    .stack:active {
        transform: scale(0.95);
    }
</style>