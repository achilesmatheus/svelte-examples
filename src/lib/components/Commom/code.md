```sv
<script>
	let showText = true

    function foo() {
        const a = 42
        const b = 'Prism'
    }
</script>

<!-- Se showText for true, então o elemento p será exibido na tela -->
{#if showText}
	<p>O Texto está escondido</p>
	<button on:click={() => showText = !showText}>Mostrar texto</button>
{:else}
	<p>Agora o Texto aparece</p>
	<button on:click={() => showText = !showText}>Esconder texto</button>
{/if}
```
