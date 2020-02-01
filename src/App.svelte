<script>
    import { SmileIcon } from "svelte-feather-icons";
    import { Router, Route, Link, router } from "yrv";

    // for the sake of simplicity
    // remove if you have SSR and want to use it with the router
    Router.hashchange = true;

    import Counter from "./pages/Counter.svelte";
</script>

<style>
    :global(body) {
        @apply bg-gray-100;
    }
</style>

<div class="flex flex-col h-screen w-full items-center">
    <nav class="self-center">
        <ul class="flex justify-between">
            <li class="p-4 text-blue-700 underline">
                <Link href="/">Hello</Link>
            </li>
            <li class="p-4 text-blue-700 underline">
                <Link href="/counter">Counter</Link>
            </li>
        </ul>
    </nav>
    <div class="h-screen w-full flex flex-col items-center justify-center ">
        <Router>
            <Route exact>
                <h1 class="text-6xl">Hello world!</h1>
            </Route>
            <Route path="/counter">
                <Counter />
            </Route>
            <Route fallback>
                <h1 class="text-6xl text-red-600">Not Found!</h1>
            </Route>
        </Router>
    </div>
</div>
