<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1>
      Placeholder Name
    </h1>
    <button class="generate">
      Generate Prompt
    </button>

    <h3>Prompt goes here</h3>

    <div class="sideNav">
      <button>
        Sign In
      </button>
      <button>
        Stats
      </button>
      <button>
        Previous
      </button>
    </div>

    <p class="wc">Word Count: ??</p>

    <form action="/action_page.php">
      <label for="entry">Entry:</label>
      <textarea id="entry" name="entry" rows="4" cols="50">Type your entry here...</textarea><br><br>
      <input type="submit" value="Submit">
    </form>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: absolute;
  top: 15%;
  left: 50%;
  transform: translate(-50%, -50%);
}

button.generate {
  font-size: 1.2rem;
  text-transform: uppercase;
  position: absolute;
  top: 25%;
  left: 50%;
  transform: translate(-50%, -50%);
}

h3 {
  font-size: 1rem;
  text-transform: uppercase;
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.sideNav {
  font-weight: 500;
  font-size: 1.4rem;
  position: absolute;
  top: 5%;
  right: 5%;
}

input[type=text] {
  width: 600px;
  height: 150px;
  padding: 5px 5px;
  margin: 0 0;
  box-sizing: border-box;
  align: center;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
