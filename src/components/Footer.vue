<script setup>
import { ref } from 'vue'

// Using CSS/Font Awesome style icons instead of Lucide
const contactInfo = {
  address: "43 Raymouth Rd. Battlemor, London 3910",
  phone1: "+1(123)-456-7890",
  phone2: "+1(123)-456-7890",
  email: "info@mydomain.com"
}

const copyrightText = "Copyright 2023, All rights reserved."
const column1Heading = "About NemoTech"
const column1Text = "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts."
const column2Heading = "Projects"
const column3Heading = "Services"
const column4Heading = "Contact"
const connectHeading = "Connect"

const socialItems = [
  {
    link: "https://www.instagram.com/",
    icon: "📷",
    name: "Instagram",
    color: "hover:bg-pink-600"
  },
  {
    link: "https://www.twitter.com/",
    icon: "🐦",
    name: "Twitter",
    color: "hover:bg-blue-500"
  },
  {
    link: "https://www.facebook.com/",
    icon: "👥",
    name: "Facebook",
    color: "hover:bg-blue-600"
  },
  {
    link: "https://www.linkedin.com/",
    icon: "💼",
    name: "LinkedIn",
    color: "hover:bg-blue-700"
  },
  {
    link: "https://www.pinterest.com/",
    icon: "📌",
    name: "Pinterest",
    color: "hover:bg-red-600"
  },
]

const projectLinks = [
  "La Lega Stadium",
  "France Building", 
  "22 New Homes",
  "Manage Center",
  "Sports Hall"
]

const serviceLinks = [
  "Architect",
  "Interior Design",
  "Landscape Design", 
  "Consultancy"
]
</script>

<template>
  <footer class="site-footer">
    <!-- Animated background dots -->
    <div class="footer-dots"></div>
    
    <!-- Main footer content -->
    <div class="footer-content">
      <div class="container">
        <div class="footer-grid">
          
          <!-- About Section -->
          <div class="footer-col footer-col-about">
            <div class="footer-widget">
              <h3 class="widget-title">{{ column1Heading }}</h3>
              <p class="widget-text">{{ column1Text }}</p>
              
              <!-- Social Media Section -->
              <div class="social-section">
                <h4 class="social-title">{{ connectHeading }}</h4>
                <div class="social-links">
                  <a 
                    v-for="(social, index) in socialItems" 
                    :key="index"
                    :href="social.link" 
                    :title="social.name"
                    class="social-link"
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    <span class="social-icon">{{ social.icon }}</span>
                  </a>
                </div>
              </div>
            </div>
          </div>

          <!-- Projects Section -->
          <div class="footer-col">
            <div class="footer-widget">
              <h3 class="widget-title">{{ column2Heading }}</h3>
              <ul class="footer-links">
                <li v-for="(project, index) in projectLinks" :key="index">
                  <a href="#" class="footer-link">{{ project }}</a>
                </li>
              </ul>
            </div>
          </div>

          <!-- Services Section -->
          <div class="footer-col">
            <div class="footer-widget">
              <h3 class="widget-title">{{ column3Heading }}</h3>
              <ul class="footer-links">
                <li v-for="(service, index) in serviceLinks" :key="index">
                  <a href="#" class="footer-link">{{ service }}</a>
                </li>
              </ul>
            </div>
          </div>

          <!-- Contact Section -->
          <div class="footer-col footer-col-contact">
            <div class="footer-widget">
              <h3 class="widget-title">{{ column4Heading }}</h3>
              
              <div class="contact-info">
                <div class="contact-item">
                  <div class="contact-icon">
                    <span>📍</span>
                  </div>
                  <address class="contact-text">{{ contactInfo.address }}</address>
                </div>
                
                <div class="contact-item">
                  <div class="contact-icon">
                    <span>📞</span>
                  </div>
                  <div class="contact-text">
                    <a :href="'tel:' + contactInfo.phone1" class="contact-link">
                      {{ contactInfo.phone1 }}
                    </a>
                    <a :href="'tel:' + contactInfo.phone2" class="contact-link">
                      {{ contactInfo.phone2 }}
                    </a>
                  </div>
                </div>
                
                <div class="contact-item">
                  <div class="contact-icon">
                    <span>✉️</span>
                  </div>
                  <div class="contact-text">
                    <a :href="'mailto:' + contactInfo.email" class="contact-link">
                      {{ contactInfo.email }}
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer Bottom -->
    <div class="footer-bottom">
      <div class="container">
        <div class="footer-bottom-content">
          <div class="copyright">
            <p class="copyright-text">{{ copyrightText }}</p>
          </div>
          <div class="footer-bottom-links">
            <a href="#" class="bottom-link">Privacy Policy</a>
            <a href="#" class="bottom-link">Terms of Service</a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  position: relative;
  background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
  color: #ffffff;
  overflow: hidden;
}

/* Container */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

/* Animated background dots */
.footer-dots {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: radial-gradient(circle, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
  background-size: 30px 30px;
  animation: float 20s infinite linear;
  z-index: 1;
}

@keyframes float {
  0% { transform: translateX(0) translateY(0); }
  100% { transform: translateX(-30px) translateY(-30px); }
}

.footer-content {
  position: relative;
  z-index: 2;
  padding: 4rem 0 2rem;
}

/* Grid System */
.footer-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

@media (min-width: 768px) {
  .footer-grid {
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }
}

@media (min-width: 1024px) {
  .footer-grid {
    grid-template-columns: 2fr 1fr 1fr 1.5fr;
    gap: 3rem;
  }
}

.footer-widget {
  opacity: 0;
  transform: translateY(30px);
  animation: slideInUp 0.8s ease forwards;
}

.footer-col:nth-child(1) .footer-widget { animation-delay: 0.1s; }
.footer-col:nth-child(2) .footer-widget { animation-delay: 0.2s; }
.footer-col:nth-child(3) .footer-widget { animation-delay: 0.3s; }
.footer-col:nth-child(4) .footer-widget { animation-delay: 0.4s; }

@keyframes slideInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.widget-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 1.5rem;
  color: #ffffff;
  position: relative;
  padding-bottom: 0.5rem;
}

.widget-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 40px;
  height: 2px;
  background: linear-gradient(90deg, #4f46e5, #06b6d4);
  border-radius: 1px;
}

.widget-text {
  color: #cccccc;
  line-height: 1.7;
  margin-bottom: 2rem;
}

/* Social Media Styles */
.social-section {
  margin-top: 2rem;
}

.social-title {
  font-size: 1.1rem;
  font-weight: 500;
  margin-bottom: 1rem;
  color: #ffffff;
  background: linear-gradient(135deg, #4f46e5, #06b6d4);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.social-links {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  color: #ffffff;
  text-decoration: none;
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
  position: relative;
  overflow: hidden;
}

.social-link::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
  transition: left 0.5s ease;
}

.social-link:hover::before {
  left: 100%;
}

.social-link:hover {
  background: linear-gradient(135deg, #4f46e5, #06b6d4);
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(79, 70, 229, 0.3);
  color: #ffffff;
}

.social-icon {
  font-size: 1.2rem;
  position: relative;
  z-index: 2;
}

/* Footer Links */
.footer-links {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-links li {
  margin-bottom: 0.75rem;
}

.footer-link {
  color: #cccccc;
  text-decoration: none;
  transition: all 0.3s ease;
  position: relative;
  padding-left: 1rem;
  display: block;
}

.footer-link::before {
  content: '→';
  position: absolute;
  left: 0;
  opacity: 0;
  transition: all 0.3s ease;
  color: #06b6d4;
}

.footer-link:hover {
  color: #06b6d4;
  padding-left: 1.5rem;
  transform: translateX(2px);
}

.footer-link:hover::before {
  opacity: 1;
}

/* Contact Info Styles */
.contact-info {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.contact-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  transition: transform 0.3s ease;
}

.contact-item:hover {
  transform: translateY(-2px);
}

.contact-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: rgba(79, 70, 229, 0.1);
  border-radius: 50%;
  flex-shrink: 0;
  margin-top: 0.25rem;
  transition: all 0.3s ease;
  border: 1px solid rgba(79, 70, 229, 0.2);
}

.contact-item:hover .contact-icon {
  background: rgba(79, 70, 229, 0.2);
  box-shadow: 0 4px 15px rgba(79, 70, 229, 0.3);
  animation: pulse-glow 2s infinite;
}

@keyframes pulse-glow {
  0%, 100% {
    box-shadow: 0 4px 15px rgba(79, 70, 229, 0.3);
  }
  50% {
    box-shadow: 0 4px 25px rgba(79, 70, 229, 0.6);
  }
}

.contact-icon span {
  font-size: 1.2rem;
}

.contact-text {
  flex: 1;
  margin: 0;
  color: #cccccc;
  line-height: 1.6;
}

.contact-text a {
  display: block;
  margin-bottom: 0.25rem;
}

.contact-link {
  color: #cccccc;
  text-decoration: none;
  transition: color 0.3s ease;
}

.contact-link:hover {
  color: #06b6d4;
}

/* Footer Bottom */
.footer-bottom {
  position: relative;
  z-index: 2;
  background: rgba(0, 0, 0, 0.3);
  padding: 1.5rem 0;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-bottom-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

@media (min-width: 768px) {
  .footer-bottom-content {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
}

.copyright-text {
  margin: 0;
  color: #999999;
  font-size: 0.9rem;
}

.footer-bottom-links {
  display: flex;
  justify-content: center;
  gap: 2rem;
}

.bottom-link {
  color: #999999;
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.3s ease;
}

.bottom-link:hover {
  color: #06b6d4;
}

/* Enhanced border gradients */
.footer-bottom::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 1px;
  background: linear-gradient(90deg, 
    transparent 0%, 
    rgba(79, 70, 229, 0.5) 50%, 
    transparent 100%
  );
  animation: breathe 4s ease-in-out infinite;
}

@keyframes breathe {
  0%, 100% {
    opacity: 0.5;
    transform: scaleX(0.8);
  }
  50% {
    opacity: 1;
    transform: scaleX(1);
  }
}

/* Responsive adjustments */
@media (max-width: 767px) {
  .footer-content {
    padding: 3rem 0 1.5rem;
  }
  
  .social-links {
    justify-content: center;
  }
  
  .contact-item {
    align-items: center;
  }
  
  .contact-icon {
    margin-top: 0;
  }
  
  .footer-col-about {
    text-align: center;
  }
  
  .widget-title::after {
    left: 50%;
    transform: translateX(-50%);
  }
}

@media (min-width: 768px) and (max-width: 1023px) {
  .footer-col-about {
    grid-column: span 2;
  }
}
</style>
