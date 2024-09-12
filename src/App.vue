<template>
  <div id="app">
    <h1>Assyfaul Khoiriyah</h1>

    <!-- Click Counter -->
    <div class="counter-section">
      <h2>Click Counter</h2>
      <button class="counter-button" @click="incrementCounter">Click me</button>
      <p>Button clicked {{ counter }} times.</p>
    </div>

    <!-- Box Color Changer -->
    <div class="color-changer-section">
      <h2>Box Color Changer</h2>
      <div class="color-box" :style="{ backgroundColor: boxColor }"></div>
      <button class="color-change-button" @click="changeColor">Change Color</button>
    </div>

    <!-- Image Carousel -->
    <div class="carousel-section">
      <h2>Image Carousel</h2>
      <div class="carousel">
        <img :src="images[currentImage]" alt="Carousel Image" />
      </div>
      <button class="carousel-button" @click="previousImage">Previous</button>
      <button class="carousel-button" @click="nextImage">Next</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Click Counter Data
      counter: 0,

      // Box Color Changer Data
      colors: ["red", "green", "blue", "yellow"],
      currentColorIndex: 0,
      boxColor: "red",

      // Image Carousel Data
      images: [
        "https://i.pinimg.com/564x/de/58/10/de5810941ea0ad6988bdf3eff395362e.jpg",
        "https://i.pinimg.com/564x/eb/36/ff/eb36ff883a983208680ac407c157ce2f.jpg",
        "https://i.pinimg.com/564x/6c/05/f1/6c05f19ab1d1872649e888f42ac84dbc.jpg"
      ],
      currentImage: 0
    };
  },
  methods: {
    // Click Counter Method
    incrementCounter() {
      this.counter++;
    },
    // Box Color Changer Method
    changeColor() {
      this.currentColorIndex = (this.currentColorIndex + 1) % this.colors.length;
      this.boxColor = this.colors[this.currentColorIndex];
    },
    // Image Carousel Methods
    nextImage() {
      this.currentImage = (this.currentImage + 1) % this.images.length;
    },
    previousImage() {
      this.currentImage = (this.currentImage - 1 + this.images.length) % this.images.length;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 50px;
}

/* Click Counter Section */
.counter-section {
  margin-bottom: 30px;
}

.counter-button {
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.counter-button:hover {
  background-color: #45a049;
}

/* Box Color Changer Section */
.color-changer-section {
  margin-bottom: 30px;
}

.color-box {
  width: 100px;
  height: 100px;
  margin: 20px auto;
  transition: background-color 0.3s;
}

.color-change-button {
  background-color: #2196F3;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.color-change-button:hover {
  background-color: #1976D2;
}

/* Image Carousel Section */
.carousel-section {
  margin-bottom: 30px;
}

.carousel {
  margin: 20px auto;
}

.carousel img {
  width: 200px;
  height: 200px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.carousel-button {
  background-color: #FF5722;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s;
  margin: 5px;
}

.carousel-button:hover {
  background-color: #E64A19;
}
</style>
