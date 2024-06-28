<template>
  <div class="landing-container">
    <!-- Шапка сайта -->
    <header class="header">
      <div class="logo" @click="scrollToTop">
        <img src="@/assets/logoo.png" alt="БрендКроссовок" class="logo-image" />
      </div>
      <nav class="nav">
        <ul>
          <li><a href="#features">Забавности</a></li>
          <li><a href="#catalog">Товар(недорого)</a></li>
          <li><a href="#news">Чекаво</a></li>
          <li><a href="#contact">На связи</a></li>
        </ul>
      </nav>
    </header>
    <!-- Герой секция с основным слоганом и кнопкой -->
    <section class="hero">
      <div class="hero-content">
        <h1>Лее брат, такие тяги ты себе еще не представлял даже</h1>
        <p>Попробуешь эти схороходы и вообще забудешь, что такое ходить, летать будешь!.</p>
        <button class="cta-button" @click="scrollToCatalog">Беру</button>
      </div>
    </section>
    <!-- Секция с особенностями продукта -->
    <section id="features" class="features">
      <h2>Забавности</h2>
      <div class="features-grid">
        <div class="feature">
          <h3>Комфорт</h3>
          <p>По кайфу</p>
        </div>
        <div class="feature">
          <h3>Стиль</h3>
          <p>Все будут смотреть в сторону се.. Ой твоей обуви</p>
        </div>
        <div class="feature">
          <h3>Долговечность</h3>
          <p>Вечные</p>
        </div>
      </div>
    </section>
    <!-- Секция с каталогом товаров -->
    <section id="catalog" class="catalog">
      <h2>Товар(недорого)</h2>
      <swiper :slides-per-view="3" space-between="30">
        <swiper-slide v-for="product in products" :key="product.id">
          <div class="product">
            <!-- Изображение продукта -->
            <img :src="product.image" :alt="product.name" class="product-image" />
            <p>{{ product.name }}</p>
            <button class="add-to-cart-button" @click="addToCart(product)">
              ${{ product.price }}
            </button>
          </div>
        </swiper-slide>
      </swiper>
    </section>
    <!-- Секция с новостями -->
    <section id="news" class="news">
      <h2>Чекаво</h2>
      <div class="news-grid">
        <div class="news-item">
          <h3>Последние выпуски</h3>
          <p>Ознакомьтесь с нашей последней коллекцией ракетоносцев</p>
        </div>
        <div class="news-item">
          <h3>Предстоящие события</h3>
          <p>У нас тут сходка на шапокляках намечается</p>
        </div>
        <div class="news-item">
          <h3>Эксклюзивные предложения</h3>
          <p>Купи одни тяги, а две банки охоты крепкой будут в подарок!</p>
        </div>
      </div>
    </section>
    <!-- Секция с контактной формой -->
    <section id="contact" class="contact">
      <h2>На связи</h2>
      <form class="contact-form">
        <input type="text" placeholder="Имя" />
        <input type="email" placeholder="Эл. почта" />
        <textarea placeholder="Сообщение"></textarea>
        <button type="submit">Отправить</button>
      </form>
    </section>
    <!-- Подвал сайта -->
    <footer class="footer">
      <p>&copy; 2024 Скороносцы. Права защищены(и не только мужские).</p>
    </footer>
  </div>
</template>

<script>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/swiper-bundle.css'

import sneakers1 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers1.jpg'
import sneakers2 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers2.jpg'
import sneakers3 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers3.jpg'
import sneakers4 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers4.jpg'
import sneakers5 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers5.jpg'
import sneakers6 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers6.jpg'
import sneakers7 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers7.jpg'
import sneakers8 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers8.jpeg'
import sneakers9 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers9.jpg'
import sneakers10 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers10.jpg'
import sneakers11 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers11.png'
import sneakers12 from 'C:/Users/bobri/Desktop/Crossovki/vue-sneakers/src/assets/sneakers12.jpg'

export default {
  name: 'SneakerLanding',
  components: {
    Swiper,
    SwiperSlide
  },
  setup() {
    // Список продуктов
    const products = ref([
      { id: 1, name: 'Подкрадули', price: 100, image: sneakers1 },
      { id: 2, name: 'Змей(белый)', price: 110, image: sneakers2 },
      { id: 3, name: 'Пчелоносцы', price: 120, image: sneakers3 },
      { id: 4, name: 'Древолазы', price: 130, image: sneakers4 },
      { id: 5, name: 'Баленсиаги', price: 140, image: sneakers5 },
      { id: 6, name: 'Змей(темный)', price: 150, image: sneakers6 },
      { id: 7, name: 'Лимузины', price: 160, image: sneakers7 },
      { id: 8, name: 'Водоплавы', price: 170, image: sneakers8 },
      { id: 9, name: 'Рахатлукумы', price: 180, image: sneakers9 },
      { id: 10, name: 'Мерин 20 века', price: 190, image: sneakers10 },
      { id: 11, name: 'Подпивасы', price: 200, image: sneakers11 },
      { id: 12, name: 'Бээмвэхи', price: 210, image: sneakers12 }
    ])

    // Корзина для добавления продуктов
    const cart = ref([])

    // Функция добавления продукта в корзину
    const addToCart = (product) => {
      cart.value.push(product)
      console.log(cart.value)
    }

    // Функция прокрутки наверх
    const scrollToTop = () => {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }

    // Функция прокрутки до каталога
    const scrollToCatalog = () => {
      document.getElementById('catalog').scrollIntoView({ behavior: 'smooth' })
    }

    return {
      products,
      addToCart,
      scrollToTop,
      scrollToCatalog
    }
  }
}
</script>

<style scoped>
/* Общий стиль сайта */
.landing-container {
  font-family: 'Playfair Display', serif;
  background:
    url('https://www.transparenttextures.com/patterns/asfalt-light.png') repeat,
    #3e2723;
  color: #d4af37;
}

/* Стиль шапки сайта */
.header {
  display: flex;
  justify-content: space-between; /* Выровнять содержимое по бокам */
  align-items: center;
  padding: 20px;
  background: #5d4037;
  color: #d4af37;
  border-bottom: 2px solid #d4af37;
  position: fixed;
  top: 0;
  width: 83.27%; /* Ограничиваем ширину шапки */
  left: 8.35%; /* Центрируем шапку по горизонтали */
  z-index: 1000;
  box-sizing: border-box; /* Добавлено, чтобы padding учитывался */
}

.logo {
  font-size: 1px;
  font-weight: bold;
  cursor: pointer; /* Добавлено для указания на кликабельность */
}

.logo-image {
  max-height: 50px; /* Задайте высоту логотипа по вашему усмотрению */
}

/* Навигация */
.nav ul {
  list-style: none;
  display: flex;
  gap: 20px;
  margin: 0; /* Убираем отступы */
}

.nav a {
  color: #d4af37;
  text-decoration: none;
  transition: color 0.3s ease;
}

.nav a:hover {
  color: #fff;
}

/* Герой секция */
.hero {
  background: linear-gradient(to bottom, #6d4c41, #3e2723);
  height: 80vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 0 20px;
  color: #fff;
  border-bottom: 2px solid #d4af37;
  margin-top: 60px; /* Отступ для шапки */
}

/* Контент в герое */
.hero-content {
  max-width: 600px;
}

/* Кнопка призыва к действию */
.cta-button {
  background: #d4af37;
  border: none;
  padding: 10px 20px;
  color: #3e2723;
  font-size: 16px;
  cursor: pointer;
  margin-top: 20px;
  transition: background 0.3s ease;
}

.cta-button:hover {
  background: #b8860b;
}

/* Секции сайта */
.features,
.catalog,
.contact,
.news {
  padding: 60px 20px;
  text-align: center;
}

/* Заголовки секций */
.features h2,
.catalog h2,
.news h2,
.contact h2 {
  font-size: 36px; /* Увеличение размера текста для заголовков секций */
  margin-bottom: 30px;
}

/* Сетки для особенностей и новостей */
.features-grid,
.news-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 30px;
}

/* Элементы особенностей, каталога и новостей */
.feature,
.catalog-item,
.news-item {
  background: #5d4037;
  padding: 10%;
  border-radius: 40px;
  color: #d4af37;
  font-size: 24px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;
}

.feature:hover,
.catalog-item:hover,
.news-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
}

/* Сетка каталога */
.catalog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 30px;
}

/* Стиль продуктов в каталоге */
.product {
  text-align: center;
  position: relative;
  padding-bottom: 70px; /* Добавление места для кнопки */
}

/* Стиль текста для названий продуктов */
.product p {
  font-size: 20px; /* Увеличение размера текста для названий продуктов */
  margin: 10px 0; /* Добавление отступов сверху и снизу */
}

/* Стиль изображения продукта */
.product-image {
  max-width: 100%; /* Устанавливает максимальную ширину изображения */
  height: auto; /* Сохраняет пропорции изображения */
  margin-bottom: 10px; /* Отступ снизу для изображения */
}

/* Кнопка добавления в корзину */
.add-to-cart-button {
  background: #d4af37;
  border: none;
  padding: 10px 10px; /* Увеличение по горизонтали и уменьшение по вертикали */
  color: #3e2723;
  font-size: 20px;
  cursor: pointer;
  border-radius: 14px; /* Закругленные углы */
  position: absolute;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
  transition: background 0.3s ease;
}

/* Стиль формы контактов */
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  max-width: 400px;
  margin: 0 auto;
}

.contact-form input,
.contact-form textarea {
  padding: 10px;
  border: 1px solid #d4af37;
  border-radius: 5px;
  background: #333;
  color: #d4af37;
}

.contact-form button {
  background: #d4af37;
  border: none;
  padding: 10px;
  color: #000;
  font-size: 16px;
  cursor: pointer;
}

/* Стиль подвала сайта */
.footer {
  background: #5d4037;
  color: #d4af37;
  padding: 20px;
  text-align: center;
  border-top: 2px solid #d4af37;
}
</style>
