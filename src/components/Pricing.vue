<script setup>
import { themeColor } from "../data/items";
const heading = "Pricing";
const subHeading = "Pricing for everyone. Choose your plan now!";
const startButtonName = "Get Started";
const packages = [
  {
    name: "Free",
    price: "0",
  },
  {
    name: "Standard",
    price: "19.99",
  },
  {
    name: "Premium",
    price: "79.99",
  },
];
</script>

<template>
  <div class="untree_co-section bg-light" id="pricing-section">
    <div class="container">
      <div class="row pricing-title">
        <div class="col-12 text-center" data-aos="fade-up" data-aos-delay="0">
          <h2 class="heading animated-heading">{{ heading }}</h2>
          <p class="animated-subheading">{{ subHeading }}</p>
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-lg-10">
          <div class="row">
            <div class="col-lg-4" data-aos="fade-up" data-aos-delay="100">
              <div class="pricing animated-card" data-plan="free">
                <div class="body">
                  <div class="price">
                    <span class="d-block plan">{{ packages[0].name }}</span>
                    <span class="price animated-price" :style="[{ color: themeColor }]">
                      <sup class="currency-symbol">$</sup>
                      <span class="price-number">{{ packages[0].price }}</span>
                    </span>
                  </div>
                  <ul class="list-unstyled ul-check primary mb-5 animated-features">
                    <li class="feature-item">There live the blind texts</li>
                    <li class="feature-item">Far far away behind the word</li>
                    <li class="feature-item">Far from the countries Vokalia and Consonantia</li>
                  </ul>
                  <p class="text-center mb-0">
                    <a
                      href="#"
                      class="btn btn-outline-primary animated-button"
                      :style="[
                        { borderColor: themeColor },
                      ]"
                    >
                      <span class="button-text">{{ startButtonName }}</span>
                      <span class="button-icon">→</span>
                    </a>
                  </p>
                </div>
              </div>
            </div>
            
            <div class="col-lg-4" data-aos="fade-up" data-aos-delay="200">
              <div class="pricing active animated-card featured-card" data-plan="standard">
                <div class="popular-badge">Most Popular</div>
                <div class="body">
                  <div class="price">
                    <span class="d-block plan">{{ packages[1].name }}</span>
                    <span class="price animated-price" :style="[{ color: themeColor }]">
                      <sup class="currency-symbol">$</sup>
                      <span class="price-number">{{ packages[1].price }}</span>
                    </span>
                  </div>
                  <ul class="list-unstyled ul-check primary mb-5 animated-features">
                    <li class="feature-item">There live the blind texts</li>
                    <li class="feature-item">Far far away behind the word</li>
                    <li class="feature-item">Far from the countries Vokalia and Consonantia</li>
                  </ul>
                  <p class="text-center mb-0">
                    <a
                      href="#"
                      class="btn btn-primary animated-button featured-button"
                      :style="[
                        { backgroundColor: themeColor },
                        { borderColor: themeColor },
                      ]"
                    >
                      <span class="button-text">{{ startButtonName }}</span>
                      <span class="button-icon">→</span>
                    </a>
                  </p>
                </div>
              </div>
            </div>
            
            <div class="col-lg-4" data-aos="fade-up" data-aos-delay="300">
              <div class="pricing animated-card" data-plan="premium">
                <div class="body">
                  <div class="price">
                    <span class="d-block plan">{{ packages[2].name }}</span>
                    <span class="price animated-price" :style="[{ color: themeColor }]">
                      <sup class="currency-symbol">$</sup>
                      <span class="price-number">{{ packages[2].price }}</span>
                    </span>
                  </div>
                  <ul class="list-unstyled ul-check primary mb-5 animated-features">
                    <li class="feature-item">There live the blind texts</li>
                    <li class="feature-item">Far far away behind the word</li>
                    <li class="feature-item">Far from the countries Vokalia and Consonantia</li>
                  </ul>
                  <p class="text-center mb-0">
                    <a
                      href="#"
                      class="btn btn-outline-primary animated-button"
                      :style="[
                        { borderColor: themeColor },
                      ]"
                    >
                      <span class="button-text">{{ startButtonName }}</span>
                      <span class="button-icon">→</span>
                    </a>
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Heading Animations */
.animated-heading {
  animation: slideInDown 1s ease-out;
  background: linear-gradient(45deg, #333, #666, #333);
  background-size: 300% 300%;
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: slideInDown 1s ease-out, gradientShift 3s ease-in-out infinite;
}

.animated-subheading {
  animation: fadeInUp 1s ease-out 0.3s both;
  opacity: 0;
}

/* Card Animations */
.animated-card {
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.animated-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s;
  z-index: 1;
}

.animated-card:hover::before {
  left: 100%;
}

.animated-card:hover {
  transform: translateY(-10px) scale(1.02);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

/* Featured Card Special Effects */
.featured-card {
  transform: scale(1.05);
  z-index: 2;
  position: relative;
}

.featured-card::after {
  content: '';
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4, #feca57);
  border-radius: 17px;
  z-index: -1;
  animation: rotateBorder 3s linear infinite;
}

.popular-badge {
  position: absolute;
  top: 10px;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(45deg, #ff6b6b, #ff8e8e);
  color: white;
  padding: 5px 15px;
  border-radius: 20px;
  font-size: 12px;
  font-weight: bold;
  animation: bounce 2s infinite;
  z-index: 3;
}

/* Price Animations */
.animated-price {
  display: inline-block;
  position: relative;
}

.currency-symbol {
  animation: bounce 2s infinite;
  animation-delay: 1s;
}

.price-number {
  display: inline-block;
  transition: transform 0.3s ease;
}

.animated-card:hover .price-number {
  transform: scale(1.1);
  animation: pulse 1s infinite;
}

/* Feature List Animations */
.animated-features {
  position: relative;
}

.feature-item {
  opacity: 0;
  transform: translateX(-20px);
  animation: slideInLeft 0.6s ease-out forwards;
  position: relative;
  padding-left: 25px;
}

.feature-item:nth-child(1) { animation-delay: 0.8s; }
.feature-item:nth-child(2) { animation-delay: 1s; }
.feature-item:nth-child(3) { animation-delay: 1.2s; }

.feature-item::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #4ecdc4;
  font-weight: bold;
  animation: checkMark 0.5s ease-out;
  animation-delay: inherit;
}

/* Button Animations */
.animated-button {
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
  border-radius: 25px;
  padding: 12px 30px;
  font-weight: 600;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 8px;
}

.button-icon {
  transition: transform 0.3s ease;
  font-weight: bold;
}

.animated-button:hover .button-icon {
  transform: translateX(5px);
}

.animated-button::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  transform: translate(-50%, -50%);
  transition: width 0.6s, height 0.6s;
}

.animated-button:hover::before {
  width: 300px;
  height: 300px;
}

.featured-button {
  animation: glow 2s ease-in-out infinite alternate;
}

/* Keyframe Animations */
@keyframes slideInDown {
  from {
    opacity: 0;
    transform: translateY(-30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-20px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0) translateX(-50%);
  }
  40% {
    transform: translateY(-5px) translateX(-50%);
  }
  60% {
    transform: translateY(-3px) translateX(-50%);
  }
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
  100% {
    transform: scale(1);
  }
}

@keyframes rotateBorder {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

@keyframes gradientShift {
  0%, 100% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
}

@keyframes checkMark {
  0% {
    transform: scale(0) rotate(0deg);
    opacity: 0;
  }
  50% {
    transform: scale(1.2) rotate(180deg);
    opacity: 1;
  }
  100% {
    transform: scale(1) rotate(360deg);
    opacity: 1;
  }
}

@keyframes glow {
  from {
    box-shadow: 0 0 5px rgba(78, 205, 196, 0.3);
  }
  to {
    box-shadow: 0 0 20px rgba(78, 205, 196, 0.6);
  }
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .animated-card:hover {
    transform: translateY(-5px) scale(1.01);
  }
  
  .featured-card {
    transform: scale(1.02);
  }
}

/* Additional hover effects for the entire section */
.untree_co-section {
  position: relative;
  overflow: hidden;
}

.untree_co-section::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(78, 205, 196, 0.03) 0%, transparent 70%);
  animation: floatingBackground 20s ease-in-out infinite;
  pointer-events: none;
}

@keyframes floatingBackground {
  0%, 100% {
    transform: translate(-50%, -50%) rotate(0deg);
  }
  50% {
    transform: translate(-50%, -50%) rotate(180deg);
  }
}
</style>
