<template>
  <div>
    <div class="image">
      <div>
        <div class="button-container">
          <img
            src="../assets/img/SignUpImage.jpg"
            class="card-img-top"
            alt="Skateboard"
            id="button"
          />
          <button class="position-button-left">LEFT</button>
        </div>
      </div>
      <div>
        <div>
          <img
            src="../assets/img/skatepark.jpg"
            class="card-img-top"
            alt="Skateboard"
          />
        </div>
      </div>
    </div>
    <div class="image">
      <div>
        <img
          src="../assets/img/skateboardinsun.jpg"
          class="card-img-top"
          alt="Skateboard"
        />
      </div>
      <div>
        <div class="button-container">
          <img
            src="../assets/img/jumpskate.jpg"
            class="card-img-top"
            alt="Skateboard"
          />
          <button @click="$router.push('/about')" class="position-button-right">
            Boards
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.image {
  display: flex;
  flex-direction: row;
}

.button-container {
  position: relative;
}

.position-button-right {
  position: absolute;
  bottom: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 8rem;
  height: 2rem;
  background-color: #fff;
  border-radius: 8px;
  border: 2px solid black;
}

.position-button-left {
  position: absolute;
  bottom: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 8rem;
  height: 2rem;
  background-color: #fff;
  border-radius: 8px;
  border: 2px solid black;
}

@media only screen and (min-width: 960px) {
  .position-button-left {
    bottom: 50%;
  }
  .position-button-right {
    bottom: 50%;
  }
}
</style>
