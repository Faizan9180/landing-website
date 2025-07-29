<script setup>
import { ref, onMounted } from 'vue'

const items = [
  {
    iconBg: "linear-gradient(135deg, #6fe7dd 0%, #4cc9c0 100%)",
    title: "Grow Your Business",
    description:
      "Scale your operations with data-driven strategies and proven methodologies that deliver measurable results for sustainable growth.",
    icon: "trending-up"
  },
  {
    iconBg: "linear-gradient(135deg, #ffc93c 0%, #ffb700 100%)",
    title: "Build Products",
    description:
      "Transform your ideas into market-ready solutions with our comprehensive product development and launch expertise.",
    icon: "package"
  },
  {
    iconBg: "linear-gradient(135deg, #f73859 0%, #e91e63 100%)",
    title: "Success Each Day",
    description:
      "Achieve consistent progress with our daily optimization strategies and performance tracking systems.",
    icon: "target"
  },
  {
    iconBg: "linear-gradient(135deg, #667eea 0%, #764ba2 100%)",
    title: "Bring Ideas to Life",
    description:
      "Turn your vision into reality with innovative design thinking and cutting-edge technology solutions.",
    icon: "lightbulb"
  },
];

const sectionRef = ref(null)
const isVisible = ref(false)

onMounted(() => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        isVisible.value = true
      }
    },
    { threshold: 0.1 }
  )
  
  if (sectionRef.value) {
    observer.observe(sectionRef.value)
  }
})

const getIcon = (iconName) => {
  const icons = {
    'trending-up': `<path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m3 17 6-6 4 4 8-8m-8 8-4-4-6 6m8-8h-8m0 0v8"/>`,
    'package': `<path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16Z"/><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m3.3 7 8.7 5 8.7-5M12 22V12"/>`,
    'target': `<circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2" fill="none"/><circle cx="12" cy="12" r="6" stroke="currentColor" stroke-width="2" fill="none"/><circle cx="12" cy="12" r="2" stroke="currentColor" stroke-width="2" fill="none"/>`,
    'lightbulb': `<path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 21h6m-6 0v-2m6 2v-2m-3-6v6m0-6a5 5 0 1 1 0 0Z"/>`
  }
  return icons[iconName] || icons['lightbulb']
}
</script>

<template>
  <div class="untree_co-section modern-features-section" ref="sectionRef">
    <div class="container">
      <!-- Section Header -->
      <div class="row mb-5">
        <div class="col-12 text-center">
          <div class="section-header" :class="{ 'animate-in': isVisible }">
            <span class="section-badge">Our Services</span>
            <h2 class="section-title">Everything You Need to Succeed</h2>
            <p class="section-subtitle">Comprehensive solutions designed to accelerate your business growth and transform your digital presence.</p>
          </div>
        </div>
      </div>

      <div class="row">
        <div
          v-for="(item, index) in items"
          :key="index"
          class="col-md-6 mb-4 mb-lg-0 col-lg-3"
          data-aos="fade-up"
          :data-aos-delay="index * 100"
        >
          <div class="modern-service" :class="{ 'animate-card': isVisible }">
            <div class="service-card">
              <div class="service-icon-wrapper">
                <div class="service-icon modern-icon" :style="{ background: item.iconBg }">
                  <svg
                    class="icon-svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <g v-html="getIcon(item.icon)"></g>
                  </svg>
                </div>
                <div class="icon-bg-blur" :style="{ background: item.iconBg }"></div>
              </div>
              
              <div class="service-contents">
                <h3 class="service-title">{{ item.title }}</h3>
                <p class="service-description">{{ item.description }}</p>
                
                <div class="service-link">
                  <span>Learn More</span>
                  <svg class="arrow-icon" width="16" height="16" viewBox="0 0 24 24" fill="none">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 17l10-10M17 7H7v10"/>
                  </svg>
                </div>
              </div>

              <!-- Hover overlay -->
              <div class="hover-overlay" :style="{ background: item.iconBg }"></div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Background Elements -->
    <div class="bg-elements">
      <div class="floating-element element-1"></div>
      <div class="floating-element element-2"></div>
      <div class="floating-element element-3"></div>
    </div>
  </div>
</template>

<style scoped>
.modern-features-section {
  padding: 120px 0;
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
  position: relative;
  overflow: hidden;
}

.bg-elements {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 0;
}

.floating-element {
  position: absolute;
  border-radius: 50%;
  opacity: 0.1;
  animation: float 6s ease-in-out infinite;
}

.element-1 {
  width: 200px;
  height: 200px;
  background: linear-gradient(135deg, #667eea, #764ba2);
  top: 10%;
  left: -100px;
  animation-delay: 0s;
}

.element-2 {
  width: 150px;
  height: 150px;
  background: linear-gradient(135deg, #6fe7dd, #4cc9c0);
  top: 60%;
  right: -75px;
  animation-delay: 2s;
}

.element-3 {
  width: 100px;
  height: 100px;
  background: linear-gradient(135deg, #ffc93c, #ffb700);
  bottom: 20%;
  left: 50%;
  animation-delay: 4s;
}

.section-header {
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s ease;
}

.section-header.animate-in {
  opacity: 1;
  transform: translateY(0);
}

.section-badge {
  display: inline-block;
  padding: 8px 20px;
  background: linear-gradient(135deg, #667eea, #764ba2);
  color: white;
  border-radius: 50px;
  font-size: 0.9rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 20px;
}

.section-title {
  font-size: 3rem;
  font-weight: 700;
  color: #2d3748;
  margin-bottom: 20px;
  letter-spacing: -0.02em;
  line-height: 1.2;
}

.section-subtitle {
  font-size: 1.2rem;
  color: #718096;
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.7;
}

.modern-service {
  height: 100%;
  opacity: 0;
  transform: translateY(50px);
  transition: all 0.6s ease;
  position: relative;
  z-index: 1;
}

.modern-service.animate-card {
  opacity: 1;
  transform: translateY(0);
}

.modern-service:nth-child(2) { transition-delay: 0.1s; }
.modern-service:nth-child(3) { transition-delay: 0.2s; }
.modern-service:nth-child(4) { transition-delay: 0.3s; }

.service-card {
  background: white;
  border-radius: 24px;
  padding: 40px 30px;
  height: 100%;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
  transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  position: relative;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  cursor: pointer;
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 25px 60px rgba(0, 0, 0, 0.15);
}

.service-card:hover .hover-overlay {
  opacity: 0.03;
}

.service-card:hover .service-icon {
  transform: scale(1.1) rotate(5deg);
}

.service-card:hover .arrow-icon {
  transform: translate(4px, -4px);
}

.service-card:hover .icon-bg-blur {
  transform: scale(1.5);
  opacity: 0.2;
}

.hover-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.service-icon-wrapper {
  position: relative;
  margin-bottom: 30px;
  display: flex;
  justify-content: center;
}

.service-icon {
  width: 80px;
  height: 80px;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  position: relative;
  z-index: 2;
  transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}

.icon-bg-blur {
  position: absolute;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  top: 10px;
  left: 50%;
  transform: translateX(-50%);
  opacity: 0.1;
  filter: blur(20px);
  transition: all 0.4s ease;
  z-index: 1;
}

.icon-svg {
  width: 32px;
  height: 32px;
}

.service-contents {
  text-align: center;
}

.service-title {
  font-size: 1.4rem;
  font-weight: 600;
  color: #2d3748;
  margin-bottom: 16px;
  line-height: 1.3;
}

.service-description {
  color: #718096;
  line-height: 1.7;
  margin-bottom: 24px;
  font-size: 1rem;
}

.service-link {
  display: inline-flex;
  align-items: center;
  color: #667eea;
  font-weight: 600;
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
}

.arrow-icon {
  margin-left: 8px;
  transition: transform 0.3s ease;
}

/* Animations */
@keyframes float {
  0%, 100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-20px) rotate(180deg);
  }
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .modern-features-section {
    padding: 80px 0;
  }

  .section-title {
    font-size: 2.5rem;
  }

  .service-card {
    padding: 30px 25px;
    margin-bottom: 30px;
  }

  .service-icon {
    width: 70px;
    height: 70px;
  }

  .floating-element {
    display: none;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: 2rem;
  }

  .service-card {
    padding: 25px 20px;
  }
}
</style>
