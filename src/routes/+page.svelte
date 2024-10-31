<script lang="ts">
    import { commands } from "../bindings";

    let name = "";
    let greetMsg = "";

    async function greet() {
        greetMsg = await commands.helloWorld(name);
    }
</script>

<div class="hero bg-base-200 min-h-screen">
    <div class="hero-content text-center">
        <div class="max-w-md">
            <form class="flex justify-center" on:submit|preventDefault={greet}>
                <input type="text" placeholder="Enter a name..." class="input input-bordered w-full max-w-xs" bind:value={name} />
                <button type="submit" class="btn btn-accent ml-2">Greet</button>
            </form>
            
            <p>{greetMsg}</p>
        </div>
    </div>
</div>
