<script lang="ts">
    import {AppBar, LightSwitch} from "@skeletonlabs/skeleton";
    import {page} from "$app/stores";

</script>

<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end" slotLead="place-content-start">
    <svelte:fragment slot="lead">
        <h1 class="h2">Promethium Network</h1>
    </svelte:fragment>
    <nav class="flex justify-center space-x-5">
        <a href="/" class="btn variant-ghost-primary">
            Home
        </a>
        <a href="/about" class="btn variant-ghost-primary">
            About
        </a>
        <a href="/rules" class="btn variant-ghost-primary">
            Rules
        </a>
        <a href="https://store.promethium-network.net" class="btn variant-ghost-primary" target="_blank">
            Webstore
        </a>
    </nav>
    <svelte:fragment slot="trail">
        <LightSwitch />
    </svelte:fragment>
</AppBar>