<template>
  <div class="greetings">
    <div class="prompt-display">
      <button class="generate">
        Generate Prompt
      </button>

      <h3>Prompt goes here</h3>
    </div>

    <div class="write-here">
      <div class="wc-plus-label">
        <p class="label">Entry:</p>
        <p class="wc">Word Count: ??</p>
      </div>

      <form action="/action_page.php">
        <textarea id="entry" name="entry" rows="4" cols="50">Type your entry here...</textarea>
        <input type="submit" value="Submit" id="entry-submit">
      </form>
    </div>
  </div>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');

.greetings {
  border: 2px solid #6fcfde;
  align-items: center;
  font-family: montserrat;
}

.prompt-display {
  position: relative;
  align-items: center;
  justify-content: center;
  width: 700px;
  text-align: center;
  margin-bottom: 20px;
}

button.generate {
  font-size: 20px;
  text-transform: uppercase;
  display: block;
  margin: 0px auto 25px auto;
  background-color: #6fcfde;
  border: 2px solid;
  color: black;
  border-radius: 15px;
  padding: 5px 15px 5px 15px;
  cursor: pointer;
}

button.generate:hover {
  background-color: #bef6ff;
}

h3 {
  font-size: 15px;
  display: block;
  color: #396c74;
}

.wc-plus-label{
  display: flex;
  justify-content: space-between;
  font-size: 14px;
  color: rgb(166, 163, 83);
}

.wc{
  display: block;
}

#entry-submit {
  float: right;
  background-color: #6fcfde;
  border: 1px solid;
  color: black;
  border-radius: 15px;
  cursor: pointer;
}

#entry-submit:hover {
  background-color: #bef6ff;
}

textarea {
  width: 100%;
  height: 150px;
  font-family: montserrat;
  font-size: 14px;
  color: #396c74;
}

</style>
