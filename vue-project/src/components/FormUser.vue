<template>
  <div class="form-container">
    <h2>Volum</h2>
    <h3>Current {{ volume }}</h3>

    <div>
      <button @click="volume++">Increase</button>
      <button @click="volume--">Decrease</button>
    </div>

    <h1>Wellcome {{ fullname }} we gonna send you the catalaog soon</h1>
    <form>
      <div class="form-group">
        <label for="exampleInputEmail1">first name: {{ first }} </label>
        <input
          type="text"
          v-model="first"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
          placeholder="Enter email"
        />
        <small id="emailHelp" class="form-text text-muted"
          >We'll never share your email with anyone else.</small
        >
      </div>
      <div class="form-group">
        <label for="exampleInputPassword1">Last name: {{ last }}</label>
        <input
          type="text"
          v-model="last"
          class="form-control"
          id="exampleInputPassword1"
          placeholder="Password"
        />
      </div>
      <div class="form-group form-check">
        <input type="checkbox" class="form-check-input" id="exampleCheck1" />
        <label class="form-check-label" for="exampleCheck1">Check me out</label>
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      first: "",
      last: "",
      volume: 0,
    };
  },
  computed: {
    fullname: function () {
      return this.first + "" + this.last;
    },
  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert("wow");
      }
    },
  },
};
</script>

<style>
.form-container {
  background-color: aqua;
  width: 50%;
  height: 50%;
  margin: 10rem;
}
.mb-3 {
  margin: 5rem;
}
</style>
