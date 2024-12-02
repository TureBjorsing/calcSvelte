<section>
    <button value=7 on:click>7</button>
    <button value=8 on:click>8</button>
    <button value=9 on:click>9</button>
    <button value="+" on:click>+</button>

    <button value=4 on:click>4</button>
    <button value=5 on:click>5</button>
    <button value=6 on:click>6</button>
    <button value="-" on:click>-</button>

    <button value=1 on:click>1</button>
    <button value=2 on:click>2</button>
    <button value=3 on:click>3</button>
    <button value="x" on:click>x</button>
    
    <button value="." on:click>,</button>
    <button value=0 on:click>0</button>
    <button value="=" on:click>=</button>
    <button value="/" on:click>/</button>
    <button value=ac on:click style = 'grid-column: span 4;'>CLEAR</button>
</section>

<style lang="scss">
    section {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-auto-rows: minmax(7rem, auto);
        grid-gap: 0.2rem;

        button {
            font-size: 5rem;
        }
    }
</style>