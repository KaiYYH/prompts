<template>
    <div class="Title">
      <h1>
        Placeholder Name
      </h1>
    </div>

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

  </template>
  
  <script>
      export default {
          name: 'NavBar',
          data() {
              return {
  
              }
          }
      }
  </script>
  
  <style scoped>

    h1 {
    font-weight: 500;
    font-size: 40px;
    }

    .sideNav {
    font-weight: 500;
    font-size: 1.4rem;
    position: absolute;
    top: 5%;
    right: 5%;
    }

  </style>
  