<script>
    import '$lib/global.css'
    import '@fontsource/inter'
	import Gradiente from '../lib/assets/Gradiente.svelte';
	import Footer from '../lib/Footer.svelte';
</script>

<div class="app">
    <main class="main">
        <div class="container">
            <slot/>
        </div>
    </main>

    <Gradiente/>

    <Footer/>
</div>

<style>
    main {
        margin-top: 40px;
        margin-bottom: auto;
    }

    .app {
        display: flex;
        flex-direction: column;
        height: 100%;
    }
</style>

