<template>
    <div class="container"></div>

      <div class="content"></div>
        <div class="hero"></div>
          <h1>BLOG</h1>
          <p>Članci, blogovi, savjeti, zanimljive teme...</p>
          <input type="text" v-model="searchQuery" placeholder="Pretraži blogove..." class="search-bar" />

          <div class="fun-facts"></div>
            <h2>Zanimljivosti o destinacijama svijeta</h2>


</template>


<script setup>
import { ref, computed } from 'vue';
import BUDVA from "@/images/1.jpg";
import Monako from "@/images/2.jpg";
import Bar from "@/images/3.jpg";
import Bari from "@/images/4.jpg";
import Split from "@/images/5.jpg";
import Dubrovnik from "@/images/6.jpg";
import Korcula from '@/images/7.jpg';
import Torino from '@/images/8.jpg';
import Paris from '@/images/9.jpg';
import Ulcinj from '@/images/10.jpg';
import kotor from '@/images/11.jpg';
import Maldivi from '@/images/12.jpg';
import Antalija from '@/images/13.jpg';
import Porec from '@/images/14.jpg';
import Rovinj from '@/images/15.jpg';
import Njujork from '@/images/16.jpg';
import Brisel from '@/images/17.jpg';
import Bec from '@/images/18.jpg';
import Prag from '@/images/19.jpg';
import Lisabon from "@/images/20.jpg";
import Bukurest from "@/images/21.jpg";
import Nica from "@/images/22.jpg";
import Ankara from "@/images/23.jpg";
import Rim from "@/images/24.jpg";
import Zagreb from "@/images/25.jpg";
import Kijev from "@/images/26.jpg";
import Moskva from "@/images/27.jpg";

const items = ref([
  { image: BUDVA, title: "Budva grad ljbavi" },
  { image: Monako, title: "Monako, grad luksuza" },
  { image: Bar, title: "Stari crnogorski grad" },
  { image: Bari, title: "Najveca luka Italije" },
  { image: Split, title: "Najljepse odmaraliste Hrvatske" },
  { image: Dubrovnik, title: "Stari grad u Hrvartskoj" },
  { image: Korcula, title: "Predivna oaza mira" },
  { image: Torino, title: "Stari Italijanski grad" },
  { image: Paris, title: "Grad svjetlosti" },
  { image: Ulcinj, title: "Predivne plaze Crne Gore" },
  { image: kotor, title: "Drevni grad Crne Gore" },
  { image: Maldivi, title: "Oaza mira" },
  { image: Antalija, title: "Crce Turske" },
  { image: Porec, title: "Gradic na obali mora" },
  { image: Rovinj, title: "Srce Hravtske" },
  { image: Njujork, title: "Grad iluzija" },
  { image: Brisel, title: "Grad cokolade" },
  { image: Bec, title: "Carska prestonica" },
  { image: Prag, title: "uneskov grad kuture"},
  { image: Lisabon, title: "grad cvjeca" },
  { image: Bukurest, title: "balkanski Paris " },
  { image: Nica, title: " turisticka atrakcija " },
  { image: Ankara, title: "grad umjetnosti i muzike" },
  { image: Rim, title: "istoriski grad" },
  { image:Zagreb, title: "grad zanimljive arhitekture " },
  { image: Kijev, title: "GRAD zelenila" },
  { image: Moskva, title: "Moskva, carsko grad Rusije" },
]);

const searchQuery = ref('');

const filteredCities = computed(() => {
  return Cities.filter(recipe =>
    Cities.text.toLowerCase().includes(searchQuery.value.toLowerCase())
  );
});

const comment = ref('');
const rating = ref(0);
const submitted = ref(false);

const submitReview = () => {
  if (comment.value || rating.value) {
    submitted.value = true;
    setTimeout(() => {
      submitted.value = false;
      comment.value = '';
      rating.value = 0;
    }, 3000);
  }
};
</script>




<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');

.container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  width: 85%;
  margin: 0 auto;
  padding: 40px;
  background-color: #ffffff;
  border-radius: 16px;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
  font-family: 'Poppins', sans-serif;
  color: #333;
  margin-top: 80px;
}

.review-section {
  width: 100%;
  padding: 20px;
  background: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.comment-box {
  width: 100%;
  padding: 15px;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin-bottom: 10px;
  font-size: 16px;
}

.rating {
  display: flex;
  margin: 10px 0;
}

.rating span {
  font-size: 24px;
  cursor: pointer;
  color: #ddd;
}

.rating .selected {
  color: #ff7f50;
}

button {
  padding: 12px 20px;
  background-color: #ff7f50;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  margin-top: 10px;
  font-size: 16px;
  transition: background-color 0.3s ease, transform 0.2s ease;
}

button:hover {
  background-color: #ff6347;
  transform: scale(1.05);
}

.thank-you {
  margin-top: 10px;
  font-size: 18px;
  color: #4CAF50;
  font-weight: bold;
}

.content {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
  gap: 10px;
}

.hero {
  width: 95%;
  text-align: left;
}

.fun-facts {
  margin-top: 20px;
  font-size: 16px;
  color: #444;
  font-style: italic;
}

.hero h1 {
  font-size: 50px;
  color: #ff7f50;
  margin-bottom: 20px;
  font-weight: 700;
  font-style: italic;
}

.search-bar {
  width: 100%;
  padding: 15px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 15px;
  outline: none;
  margin-bottom: 20px;
  box-sizing: border-box;
  background-color: #f9f9f9;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

.search-bar:focus {
  border-color: #ff7f50;
  box-shadow: 0 0 5px rgba(255, 127, 80, 0.5);
}

.fun-facts {
  background-color: #f8f8f8;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  margin-top: 20px;
}

.fun-facts h2 {
  font-size: 24px;
  font-weight: 600;
  color: #ff7f50;
  margin-bottom: 10px;
}

.fun-facts p {
  font-size: 16px;
  color: #666;
  line-height: 1.6;
}

.image-grid {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  margin-top: 20px;
}

.image-container {
  position: relative;
  overflow: hidden;
  border-radius: 16px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.image-container:hover {
  transform: scale(1.05);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
}

.blog-image {
  width: 100%;
  height: 260px;
  object-fit: cover;
  border-radius: 16px;
}

.image-overlay {
  position: absolute;
  bottom: 0;
  width: 100%;
  background: linear-gradient(to top, rgba(0, 0, 0, 0.7), transparent);
  padding: 10px 0;
  text-align: center;
}

.image-text {
  color: #fff;
  font-size: 18px;
  font-weight: 600;
  text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.5);
}

.social-icons {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 20px;
}

.social-icon img {
  width: 40px;
  height: 40px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.social-icon img:hover {
  transform: scale(1.1);
}

</style>

