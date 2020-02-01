<script>
    let number = 0;
</script>

<button class="text-6xl cursor-pointer focus:outline-none" on:click|stopPropagation|preventDefault={() => number++ }>{number}</button>