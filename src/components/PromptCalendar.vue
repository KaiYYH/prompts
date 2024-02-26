<template>
  <div class="wrapper">
    <div class="month-header">
      <div id="left-arrow" @click="prevMonth">&lt;&lt;</div>
      {{ currentMonth }} {{ currentYear }}
      <div id="right-arrow" @click="nextMonth">>></div>
    </div>
    <div class="calendar-body">
      <div v-for="weekday in weekdays" :key="weekday" class="weekday-item">
          {{  weekday }}
      </div>
      <div v-for="(day, index) in currentMonthDays" :key="day">
        <div class="grid-item" v-if="index>=dayOffset">
          {{ day.slice(-2) }}
        </div>
        <div class="grid-item greyed" v-else></div>
      </div>
      <div v-for="(index) in (7 - (currentMonthDays.length % 7)) % 7" :key="day">
        <div class="grid-item greyed"></div>
      </div>
    </div>
  </div>
</template>

<script>
    import dayjs from "dayjs"
    import weekday from "dayjs/plugin/weekday"

    dayjs.extend(weekday)

    export default {
        name: 'PromptCalendar',
        data() {
            return {
              currentDate: dayjs(),
              weekdays: [
                "Sun",
                "Mon",
                "Tues",
                "Wed",
                "Thurs",
                "Fri",
                "Sat"
              ],
            }
        },
        computed: {
          daysInMonth() {
            return dayjs(this.currentDate).daysInMonth();
          },
          dayOffset() {
            return dayjs(`${dayjs(this.currentDate).year()}-${dayjs(this.currentDate).month() + 1}-1`).weekday();
          },
          currentMonth() {
            return dayjs(this.currentDate).format("MMMM")
          },
          currentYear() {
            return dayjs(this.currentDate).format("YYYY")
          },
          currentMonthDays() {
            let days = []
            for (let x = 0; x < this.dayOffset; x++) {
              days.push("")
            }
            for (let x = 0; x < this.daysInMonth; x++) {
              days.push(dayjs(`${dayjs(this.currentDate).year()}-${dayjs(this.currentDate).month() + 1}-${x + 1}`).format("YYYY-MM-DD"))
            }
            console.log(days)
            return days
          },
        },
        methods: {
          prevMonth() {
            this.currentDate = dayjs(this.currentDate).subtract(1, "month")
          },
          nextMonth() {
            this.currentDate = dayjs(this.currentDate).add(1, "month")
          }
        }
    }
</script>

<style scoped>
  .weekday-item {
    display: inline-block;
    text-align: center;
    background-color: white;
  }
  .grid-item {
    height: 100px;
    width: 100px;
    padding: 5px;
    display: inline-block;
    background-color: white;
  }
  .greyed {
    background-color: lightgray;
  }
  .wrapper {
    top: 0px;
  }
  .calendar-body {
    display: grid;
    grid-template-columns: 100px 100px 100px 100px 100px 100px 100px;
    grid-template-rows: 30px;
    grid-auto-rows: 100px;
    background-color: black;
    grid-gap: 2px;
    border: 2px solid black;
  }
  .month-header {
    text-align: center;
    position: relative;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  #left-arrow {
    display: inline-block;
    position: absolute;
    left: 10px;
    top: 10px;
    cursor: pointer;
  }
  #right-arrow {
    display: inline-block;
    position: absolute;
    right: 10px;
    top: 10px;
    cursor: pointer;
  }
</style>
