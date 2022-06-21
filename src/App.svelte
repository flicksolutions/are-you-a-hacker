<script>
let val = null;
const targetVal = 38;
let answerDiv, wrongDiv
const handleClick = () => {
  answerDiv.style.display = "none";
  wrongDiv.style.display = "none";

  if (val === targetVal) {
    answerDiv.style.display = "block";
  } else {
    wrongDiv.style.display = "block";
  }
}
/*$:{
  if (val === targetVal) {
      answerDiv.style.display = "block";
      wrongDiv.style.display = "none";
    }
}*/
</script>

<main>
  <label for="q">An welche Zahl denke ich gerade?</label><input type="number" id="q" bind:value={val} /> <button on:click={handleClick}>Antworten</button>

  <div class="answer" bind:this={answerDiv}>
    <b>Das ist richtig! Ich denke an {targetVal}!</b>
  </div>
  <div class="wrong" bind:this={wrongDiv}>
    <p>leider nein, daran denke ich nicht.</p>
  </div>
</main>

<style>
.wrong, .answer {
  display: none;
}

</style>
