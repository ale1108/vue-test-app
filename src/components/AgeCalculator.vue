<script>
export default {
  name: "AgeCalculator",

  data() {
    return {
      birthday: "",
      age: "",
      animal: "",
      zodiac: "",

      us: {
        select: false,
      },
    };
  },

  methods: {
    calculateAge() {
      if (this.us.select) {
        let currentDate = new Date();
        let birthDate = new Date(this.birthday);
        let difference = currentDate - birthDate;
        let age = Math.floor(difference / 31557600000);
        this.age = "You are " + age + " years old.";
      }
    },

    getZodiacSign() {
      if (this.us.select) {
        let birthDate = new Date(this.birthday);
        var year = birthDate.getFullYear();
        var calc = year % 12;
        if (calc === 0) {
          this.animal = "Monkey";
        } else if (calc === 1) {
          this.animal = "Rooster";
        } else if (calc === 2) {
          this.animal = "Dog";
        } else if (calc === 3) {
          this.animal = "Pig";
        } else if (calc === 4) {
          this.animal = "Rat";
        } else if (calc === 5) {
          this.animal = "Ox";
        } else if (calc === 6) {
          this.animal = "Tiger";
        } else if (calc === 7) {
          this.animal = "Rabbit";
        } else if (calc === 8) {
          this.animal = "Dragon";
        } else if (calc === 9) {
          this.animal = "Snake";
        } else if (calc === 10) {
          this.animal = "Horse";
        } else if (calc === 11) {
          this.animal = "Sheep";
        }
        this.zodiac = "Your Chinese zodiac sign is " + this.animal + ".";
      }
    },

    selectUs() {
      this.us.select = !this.us.select;
      this.age = "";
      this.zodiac = "";
    },
  },
};
</script>

<template>
  <section class="container">
    <div class="options">
      <button @click="selectUs">Click Here</button>
    </div>

    <form v-if="us.select">
      <label>Enter birth date:</label>
      <input type="date" v-model="birthday" :placeholder="us.birthday" />
      <button class="calculate" @click.prevent="calculateAge">
        Calculate Age
      </button>
      <button class="calculate" @click.prevent="getZodiacSign">
        Zodiac Sign
      </button>
    </form>

    <h1>{{ age }}</h1>
    <h1>{{ zodiac }}</h1>
  </section>
</template>


<style scoped>
html,
* {
  font-size: x-large;
}

.container {
  display: flex;
  width: 60vh;
  margin: 0 auto;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 10vh;
  border-radius: 2vh;
  background: rgb(168, 186, 224, 0.24);
}

.options {
  margin: 0 auto;
  width: 50vh;
  display: flex;
  justify-content: space-around;
}

button {
  height: 8vh;
  width: 18vh;
  border-radius: 1vh;
  font-size: 3vh;
  font-weight: 600;
  background-color: whitesmoke;
  color: #000000;
}

button:focus {
  color: whitesmoke;
  background-color: #2c3e509f;
}

form {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 5vh;
  color: black;
}

.calculate {
  margin-top: 2vh;
}

@media (max-width: 500px) {
  .container,
  * {
    max-width: 40vh;
  }
}
</style>