<script>
    import Keyboard from './Keyboard.svelte';

    let display = "";
    function updateDisplay(e) {
        let val = e.target.value; // Hämtar knappens värde

        if(val === "ac") { // Rensar displayen
            display = "";
        } else if(Number(val) >= 0 && Number(val) < 10 || val === ".") { // skriver in nummer
            display += val;
        }
    }
</script>

<main>
    <input type="text" value={display} disabled>
    <Keyboard on:click = {updateDisplay}/>
</main>