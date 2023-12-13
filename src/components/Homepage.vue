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
    <h1 class="green">{{ msg }}</h1>
    <h1>
      Prompts Website Holder
    </h1>
    <button>
      Generate Prompt
    </button>

    <p>Prompt: </p><p>Prompt goes here</p>

    <div>
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

    <p>Word Count: ??</p>

    <form action="/action_page.php">
      <label for="entry">Entry:</label>
      <input type="text" id="entry" name="entry"><br><br>
      <input type="submit" value="Submit">
    </form>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
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
