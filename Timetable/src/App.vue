<template>
  <div class="container">
    <h1>L3SOD B Timetable</h1>

    <label>Select Day:</label>
    <select v-model="selectedDay">
      <option v-for="day in days" :key="day" :value="day">
        {{ day }}
      </option>
    </select>

    <table border="1">
      <thead>
        <tr>
          <th>Time</th>
          <th>Module</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="slot in schedule[selectedDay]" :key="slot.time">
          <td>{{ slot.time }}</td>
          <td>{{ slot.module }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedDay: "Monday",

      days: ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],

      schedule: {
        Monday: [
          { time: "07:30 - 10:00", module: "UI/UX" },
          { time: "10:00 - 10:20", module: "Break" },
          { time: "10:20 - 12:50", module: "DJF" },
          { time: "12:50 - 14:00", module: "Lunch" }
{ time: "12:50 - 14:00", module: "Lunch" },
          { time: "14:00 - 16:00", module: "MATH" },
          { time: "16:00 - 17:40", module: "GD" }
        ],

        Tuesday: [
          { time: "07:30 - 10:00", module: "DJF" },
          { time: "10:00 - 10:20", module: "Break" },
          { time: "10:20 - 12:50", module: "DJF Practice" },
          { time: "12:50 - 14:00", module: "Lunch" },
          { time: "14:00 - 16:00", module: "CL" },
          { time: "16:00 - 17:40", module: "VC Pract" }
        ],

        Wednesday: [
          { time: "07:30 - 10:00", module: "VC" },
          { time: "10:00 - 10:20", module: "Break" },
          { time: "10:20 - 12:50", module: "DGV" },
          { time: "12:50 - 14:00", module: "Lunch" },
          { time: "14:00 - 17:40", module: "MATH" }
        ],

        Thursday: [
          { time: "07:30 - 10:00", module: "UI/UX" },
          { time: "10:00 - 10:20", module: "Break" },
          { time: "10:20 - 12:50", module: "DJF + Practice" },
          { time: "12:50 - 14:00", module: "Lunch" },
          { time: "14:00 - 17:40", module: "PHY + DJF Practice" }
        ],

        Friday: [
          { time: "07:30 - 10:00", module: "DGV" },
          { time: "10:00 - 10:20", module: "Break" },
          { time: "10:20 - 12:50", module: "FR" },
          { time: "12:50 - 14:00", module: "Lunch" },
          { time: "14:00 - 17:40", module: "Revision / Free Study" }
        ]
      }
    };
  }
};
</script>

<style scoped>
.container {
  max-width: 800px;
  margin: auto;
  font-family: Arial;
}

h1 {
  text-align: center;
}

select {
  padding: 6px;
  margin: 10px 0;
}

table {
  width: 100%;
  border-collapse: collapse;
}

th, td {
  padding: 10px;
}
</style>
