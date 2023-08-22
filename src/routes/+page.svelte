<script lang="ts">
    import {getToastStore, clipboard, popup, type ToastSettings, type PopupSettings} from "@skeletonlabs/skeleton";

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

<div class="bg-[url(/src/lib/images/bg.png)] h-full">
    <div class="flex justify-center py-40 space-x-4">
        <div class="w-2/4 space-y-8">
            <h1 class="h1 bg-gradient-to-br from-pink-500 to-violet-500 bg-clip-text text-transparent box-decoration-clone">Promethium Network</h1>
            <h3 class="whitespace-normal font-semibold h3">Promethium Network is a Minecraft server network managed and owned by Shradinx and gusbunce. It was started in early July 2023 when Geographica, a previous Minecraft server, was announced to be shutting down. Below, you can find other information about the server, such as links to our rules document and our social medias.</h3>
            <button type="button" class="btn variant-glass-primary" use:clipboard={ip} on:click={onClick} use:popup={popupHover}>play.promethium-network.net</button>
        </div>
        <div>
            <iframe src="https://discord.com/widget?id=1125940812182724698&theme=dark" width="350" height="500" allowtransparency={true} frameborder="0" sandbox="allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts" title="Discord Embed"/>
        </div>
    </div>
</div>