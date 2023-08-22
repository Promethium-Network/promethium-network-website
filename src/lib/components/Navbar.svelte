<script lang="ts">
    import {AppBar, LightSwitch, clipboard, getToastStore, type ToastSettings, popup, type PopupSettings} from "@skeletonlabs/skeleton";
    import {page} from "$app/stores";

    const t: ToastSettings = {
        message: 'The server IP has been copied to clipboard :)',
        background: 'bg-gradient-to-br variant-gradient-secondary-tertiary text-white',
    }

    const toastStore = getToastStore();

    const ip = 'play.promethium-network.net';

    const popupHover: PopupSettings = {
        event: 'hover',
        target: 'popupHover',
        placement: 'bottom'
    }

    const onClick = () => {
        toastStore.trigger(t);
    }
</script>

<div class="card p-4 variant-filled-secondary" data-popup="popupHover">
    <p>Copy IP to clipboard :)</p>
    <div class="arrow variant-filled-secondary" />
</div>

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
        <button type="button" class="btn variant-ghost-secondary" use:clipboard={ip} on:click={onClick} use:popup={popupHover}>play.promethium-network.net</button>
        <LightSwitch />
    </svelte:fragment>
</AppBar>