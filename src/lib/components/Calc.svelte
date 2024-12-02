<script>
    import Keyboard from './Keyboard.svelte';

    let num = 0;
    let newNum = false;
    let operatorOn = false;
    let operator = "";

    let display = "";
    function updateDisplay(e) {
        let val = e.target.value; // Hämtar knappens värde

        if(val === "ac") { // Rensar displayen
            display = "";
            operator = null;
            num = 0;
        } else if(Number(val) >= 0 && Number(val) < 10 || val === ".") { // skriver in nummer
            if(newNum) {
                display = "";
                newNum = false;
            }
            display += val;
        } else if(val == "=") {
            calculate(operator);
        } else {
            num = parseFloat(display);
            operator = val;
            if(operatorOn) {
                calculate(operator);
            }
            operatorOn = true;
            newNum = true;
        }
    }

    function calculate(arithmetic) {
        if(arithmetic == "+") {
            display = num + parseFloat(display);
        } else if(arithmetic == "-") {
            display = num - parseFloat(display);
        } else if(arithmetic == "x") {
            display = num * parseFloat(display);
        } else if(arithmetic == "/") {
            display = num / parseFloat(display);
        }

        operatorOn = false;
    }
</script>

<input type="text" value={display} disabled>
<Keyboard on:click = {updateDisplay}/>

<style lang="scss">
    
    input {
        width: 100%;
        font-size: 5rem;
        margin-bottom:10px;
        background-color: black;
        color: rgba(0, 255, 0, 1);
        text-align: right;
        padding: 10px 4px 10px 4px;
        font-family: lcd;
        border: 1px solid yellow;
        border-radius:4px;
    }
    
    input[disabled] {
    -webkit-text-fill-color: rgba(0, 255, 0, 1);
    opacity: 1;
    -webkit-opacity: 1;
    color: rgba(0, 255, 0, 1)
    }
</style>