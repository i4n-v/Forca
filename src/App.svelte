<script>
  import { Router, Link, Route } from 'svelte-routing';
  import { Home, Regras, Sobre, Forca } from './pages';

  export let urlRouter = window.location.pathname;
</script>

<Router url={urlRouter} basepath="/">
    <Route path="/" component={Home} />
    <Route path="/jogar" component={Forca} />
    <Route path="/como_jogar" component={Regras} />
    <Route path="/sobre" component={Sobre} />
</Router>

<style>
	
</style>