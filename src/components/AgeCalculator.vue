<script>
export default {
  name: "AgeCalculator",

  data() {
    return {
      birthday: "",
      age: "",
      animal: "",
      zodiac: "",
      sign: "",
      horoscope: "",

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

    getHoroscope() {
      if (this.us.select) {
        let birthDate = new Date(this.birthday);
        var month = birthDate.getMonth();
        var date = birthDate.getDate();

        if (month === 0) {
          if (date >= 19 && date <= 31) {
            this.sign = "Aquarius";
          }
        }
        if (month === 1) {
          if (date >= 1 && date <= 17) {
            this.sign = "Aquarius";
          }
        }

        if (month === 1) {
          if (date >= 18 && date <= 29) {
            this.sign = "Pisces";
          }
        }
        if (month === 2) {
          if (date >= 1 && date <= 19) {
            this.sign = "Pisces";
          }
        }

        if (month === 2) {
          if (date >= 20 && date <= 31) {
            this.sign = "Aries";
          }
        }
        if (month === 3) {
          if (date >= 1 && date <= 18) {
            this.sign = "Aries";
          }
        }

        if (month === 3) {
          if (date >= 19 && date <= 30) {
            this.sign = "Taurus";
          }
        }
        if (month === 4) {
          if (date >= 1 && date <= 19) {
            this.sign = "Taurus";
          }
        }

        if (month === 4) {
          if (date >= 20 && date <= 31) {
            this.sign = "Gemini";
          }
        }
        if (month === 5) {
          if (date >= 1 && date <= 19) {
            this.sign = "Gemini";
          }
        }

        if (month === 5) {
          if (date >= 20 && date <= 30) {
            this.sign = "Cancer";
          }
        }
        if (month === 6) {
          if (date >= 1 && date <= 21) {
            this.sign = "Cancer";
          }
        }

        if (month === 6) {
          if (date >= 22 && date <= 31) {
            this.sign = "Leo";
          }
        }
        if (month === 7) {
          if (date >= 1 && date <= 21) {
            this.sign = "Leo";
          }
        }

        if (month === 7) {
          if (date >= 22 && date <= 31) {
            this.sign = "Virgo";
          }
        }
        if (month === 8) {
          if (date >= 1 && date <= 21) {
            this.sign = "Virgo";
          }
        }

        if (month === 8) {
          if (date >= 22 && date <= 30) {
            this.sign = "Libra";
          }
        }
        if (month === 9) {
          if (date >= 1 && date <= 21) {
            this.sign = "Libra";
          }
        }

        if (month === 9) {
          if (date >= 22 && date <= 31) {
            this.sign = "Scorpio";
          }
        }
        if (month === 10) {
          if (date >= 1 && date <= 20) {
            this.sign = "Scorpio";
          }
        }

        if (month === 10) {
          if (date >= 21 && date <= 30) {
            this.sign = "Sagittarius";
          }
        }
        if (month === 11) {
          if (date >= 1 && date <= 20) {
            this.sign = "Sagittarius";
          }
        }

        if (month === 11) {
          if (date >= 21 && date <= 31) {
            this.sign = "Capricorn";
          }
        }
        if (month === 0) {
          if (date >= 1 && date <= 18) {
            this.sign = "Capricorn";
          }
        }

        this.horoscope = "Your astrological zodiac sign is " + this.sign + ".";
      }
    },

    selectUs() {
      this.us.select = !this.us.select;
      this.age = "";
      this.zodiac = "";
      this.horoscope = "";
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
        Chinese Zodiac
      </button>
      <button class="calculate" @click.prevent="getHoroscope">Horoscope</button>
    </form>

    <h1>{{ age }}</h1>
    <h1>{{ zodiac }}</h1>
    <h1>{{ horoscope }}</h1>
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