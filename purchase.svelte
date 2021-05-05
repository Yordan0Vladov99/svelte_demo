<script>
import { each } from "svelte/internal";

Array.prototype.sum = function (prop) {
    var total = 0
    for ( var i = 0, _len = this.length; i < _len; i++ ) {
        total += this[i][prop]
    }
    return total
}

    export let books;
    $: sum = books.sum('pages');
</script>


<style>
    ul{
        list-style: none;
        margin: 1rem;
        padding:0;
    }
    li{
        font-size:1.5rem;
        margin: 1rem;
    }
</style>

<ul>
    {#each books as book}
    <li> {book.title} - {book.pages}</li>
    {/each}
</ul>

<h1> Total : {sum} </h1>