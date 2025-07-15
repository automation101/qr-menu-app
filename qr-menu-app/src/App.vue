<template>
  <div class="app-container">
    <!-- Header -->
    <header class="app-header">
      <div class="header-bg">
        <div class="header-content">
          <img src="/logo.png" alt="Cheeseburger Bobby's Logo" class="logo" />
          <div class="restaurant-info">
            <h1>Cheeseburger Bobby's</h1>
            <p class="tagline">Fresh. Fast. Flavorful. <br />Flowery Branch, GA</p>
          </div>
        </div>
      </div>
    </header>

    <!-- Main Menu -->
    <main class="menu-section">
      <h1 class="menu-title">Our Menu</h1>

      <!-- 🍔 Burgers -->
      <section class="menu-category">
        <h2 class="category-title">🍔 Burgers</h2>
        <div class="menu-grid">
          <div class="menu-card" v-for="item in burgers" :key="item.name">
            <img :src="item.image" class="card-img" :alt="item.name" />
            <div class="card-content">
              <h3 class="card-title">{{ item.name }}</h3>
              <p class="card-desc">{{ item.desc }}</p>
              <div class="card-price">{{ item.price }}</div>
              <div class="card-price">Combo {{ item.combo }}</div>
            </div>
          </div>
        </div>
      </section>

      <!-- 🍟 Fries -->
      <section class="menu-category">
        <h2 class="category-title">🍟 Fries</h2>
        <div class="menu-grid">
          <div class="menu-card" v-for="item in fries" :key="item.name">
            <img :src="item.image" class="card-img" :alt="item.name" />
            <div class="card-content">
              <h3 class="card-title">{{ item.name }}</h3>
              <p class="card-desc">{{ item.desc }}</p>
              <div class="card-price">{{ item.price }}</div>
            </div>
          </div>
        </div>
      </section>

      <!-- 🥤 Drinks -->
      <section class="menu-category">
        <h2 class="category-title">🥤 Drinks</h2>
        <div class="menu-grid">
          <div class="menu-card" v-for="item in drinks" :key="item.name">
            <img :src="item.image" class="card-img" :alt="item.name" />
            <div class="card-content">
              <h3 class="card-title">{{ item.name }}</h3>
              <p class="card-desc">{{ item.desc }}</p>
              <div class="card-price">{{ item.price }}</div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      burgers: [
        {
          name: "Bobby's Original Burger",
          desc: "Fresh Angus beef, lettuce, tomato, pickle, Bobby sauce",
          price: "$7.99",
          image: "/images/bobby-burger.jpg",
        },
        {
          name: "Bacon Cheeseburger",
          desc: "Thick, crispy bacon and Cheddar cheese",
          price: "$8.09",
          combo: "$14.99",
          image: "/images/bacon-cheeseburger.jpg",
        },
        {
          name: "Mushroom Swiss Burger",
          desc: "Sautéed mushrooms and Swiss cheese",
          price: "$8.49",
          image: "/images/mushroom-burger.jpg",
        },
      ],
      fries: [
        {
          name: "Fresh Cut Fries",
          desc: "Crispy golden fries made in-house",
          price: "$3.69",
          image: "/images/fries.jpg",
        },
        {
          name: "Cheese Fries",
          desc: "Fries topped with creamy cheddar cheese",
          price: "$4.99",
          image: "/images/cheese-fries.jpg",
        },
      ],
      drinks: [
        {
          name: "Coca-Cola",
          desc: "Classic refreshing soda",
          price: "$3.09",
          image: "/images/coca-cola.jpg",
        },
        {
          name: "Bobby's Mom's Sweet Tea",
          desc: "Classic, homemade sweet tea. Available in medium or large.",
          price: "$2.99",
          image: "/images/sweet_tea.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Layout */
.app-container {
  font-family: 'Segoe UI', sans-serif;
  background: #fff;
  color: #222;
  margin: 0;
  padding: 0;
}

/* Awesome Header */
.app-header {
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
}
.header-bg {
  background: linear-gradient(90deg, #111827, #1f2937);
  padding: 20px 16px;
  color: white;
}
.header-content {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 16px;
}
.logo {
  height: 60px;
  width: auto;
  background: white;
  padding: 6px;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
}
.restaurant-info h1 {
  font-size: 22px;
  margin: 0;
  font-weight: 700;
  line-height: 1.2;
}
.tagline {
  font-size: 14px;
  color: #ccc;
  margin-top: 4px;
  line-height: 1.4;
}

/* Menu */
.menu-section {
  padding: 20px 16px 40px;
  max-width: 1000px;
  margin: 0 auto;
}
.menu-title {
  font-size: 24px;
  font-weight: 600;
  text-align: center;
  margin-bottom: 24px;
}
.category-title {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 16px;
}

/* Grid & Card */
.menu-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 16px;
}
.menu-card {
  display: flex;
  flex-direction: column;
  border: 1px solid #eee;
  border-radius: 12px;
  overflow: hidden;
  background: #fff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
}
.menu-card:hover {
  transform: scale(1.02);
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.1);
}
.card-img {
  width: 100%;
  height: 180px;
  object-fit: cover;
}
.card-content {
  padding: 12px 16px;
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.card-title {
  font-size: 16px;
  font-weight: 600;
  margin: 0;
}
.card-desc {
  font-size: 14px;
  color: #555;
}
.card-price {
  font-size: 15px;
  font-weight: 600;
  color: #000;
  margin-top: 4px;
}
</style>
