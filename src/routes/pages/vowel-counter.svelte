<script>
    let word = "";
    let numberOfVowels = 0;
    let percentageOfWordThatIsVowels = String.fromCodePoint(0x1f47b);
    const vowels = ["a", "e", "i", "o", "u"];

    const precision = 4;

    function preciseString(x) {
        return Number.parseFloat(x).toPrecision(precision).toString() + "%";
    }

    function calculateVowels() {
        numberOfVowels = 0;
        let numberOfSpaces = 0;
        let numberOfChars = word.length;
        let chars = word.split("");
        for (const char of chars) {
            if (vowels.includes(char)) numberOfVowels++;
            if (char === " ") numberOfSpaces++;
        }

        numberOfChars = numberOfChars - numberOfSpaces;

        percentageOfWordThatIsVowels = preciseString(
            (numberOfVowels / numberOfChars) * 100
        );

        if (isNaN(parseFloat(percentageOfWordThatIsVowels))) {
            percentageOfWordThatIsVowels = String.fromCodePoint(0x1f47b);
        }
    }

    function handleWordChange(e) {
        word = e.target.value;
        calculateVowels();
    }
</script>

<svelte:head>
    <title>Vowel Counter</title>
</svelte:head>

<div class="flexContainer">
    <h1>vowel counter</h1>
    <div class="gray">
        <h3 class="grayText">enter your word here:</h3>
        <input
            class="wordInput"
            type="text"
            id="word"
            required
            placeholder="your word here!"
            on:keyup={handleWordChange}
        />
        <h3 class="grayText marginTop">number of vowels:</h3>
        <h3 class="result">{numberOfVowels}</h3>

        <h3 class="grayText marginTop">percentage:</h3>
        <h3 class="result">{percentageOfWordThatIsVowels}</h3>
    </div>
</div>

<style>
    .flexContainer {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        font-family: Helvetica, sans-serif;
        font-size: 1.5em;
    }
    h1 {
        width: 100%;
        text-align: center;
    }
    .grayText {
        margin-top: 0px;
        background-color: rgba(200, 200, 200, 0.8);
        padding: 10px;
        border-radius: 12px;
        text-align: center;
    }
    .marginTop {
        margin-top: 20px;
    }

    .wordInput {
        display: flex;
        margin: auto;
        font-size: 1em;
    }
    .result {
        text-align: center;
    }
</style>
