<script setup>
import { ref, reactive } from 'vue'
import { themeColor, contactInfo } from "../data/items";

const heading = "Get In Touch";
const subHeading = "Ready to transform your business? Let's discuss how we can help you achieve your goals.";
const contactInfoHeading = "Contact Information";
const buttonSendMessage = "Send Message";
const labels = {
  firstName: "First Name",
  lastName: "Last Name",
  email: "Email Address",
  message: "Message",
};

// Form state
const isSubmitting = ref(false)
const formData = reactive({
  firstName: '',
  lastName: '',
  email: '',
  message: ''
})

// Submit handler
const handleSubmit = async (e) => {
  e.preventDefault()
  isSubmitting.value = true
  
  try {
    // Simulate API call
    await new Promise(resolve => setTimeout(resolve, 1500))
    
    // Reset form
    Object.keys(formData).forEach(key => {
      formData[key] = ''
    })
    
    alert('Thank you for your message! We\'ll get back to you soon.')
  } catch (error) {
    console.error('Error submitting form:', error)
  } finally {
    isSubmitting.value = false
  }
}
</script>

<template>
  <div class="untree_co-section modern-contact-section" id="contact-section">
    <div class="container">
      <div class="row mb-5" data-aos="fade-up" data-aos-delay="0">
        <div class="col-12 text-center">
          <h2 class="modern-heading">{{ heading }}</h2>
          <p class="modern-subheading">{{ subHeading }}</p>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-7">
          <div class="modern-form-container" data-aos="fade-up" data-aos-delay="100">
            <form class="contact-form modern-form" @submit="handleSubmit">
              <div class="form-header">
                <h3>Send us a message</h3>
                <p>Fill out the form below and we'll get back to you within 24 hours.</p>
              </div>
              
              <div class="row">
                <div class="col-6">
                  <div class="form-group modern-form-group">
                    <label class="modern-label" for="fname">{{ labels.firstName }}</label>
                    <input 
                      type="text" 
                      class="form-control modern-input" 
                      id="fname"
                      v-model="formData.firstName"
                      :disabled="isSubmitting"
                      required
                    />
                  </div>
                </div>
                <div class="col-6">
                  <div class="form-group modern-form-group">
                    <label class="modern-label" for="lname">{{ labels.lastName }}</label>
                    <input 
                      type="text" 
                      class="form-control modern-input" 
                      id="lname"
                      v-model="formData.lastName"
                      :disabled="isSubmitting"
                      required
                    />
                  </div>
                </div>
              </div>
              <div class="form-group modern-form-group">
                <label class="modern-label" for="email">{{ labels.email }}</label>
                <input 
                  type="email" 
                  class="form-control modern-input" 
                  id="email"
                  v-model="formData.email"
                  :disabled="isSubmitting"
                  required
                />
              </div>
              <div class="form-group modern-form-group">
                <label class="modern-label" for="message">{{ labels.message }}</label>
                <textarea
                  class="form-control modern-textarea"
                  id="message"
                  cols="30"
                  rows="5"
                  v-model="formData.message"
                  :disabled="isSubmitting"
                  placeholder="Tell us about your project..."
                  required
                ></textarea>
              </div>
              <button
                type="submit"
                class="btn btn-primary modern-btn"
                :class="{ 'loading': isSubmitting }"
                :disabled="isSubmitting"
                :style="[
                  { backgroundColor: themeColor },
                  { borderColor: themeColor },
                ]"
              >
                <span v-if="!isSubmitting">{{ buttonSendMessage }}</span>
                <span v-else>Sending...</span>
              </button>
            </form>
          </div>
        </div>
        <div class="col-lg-4 contact-section ml-auto" data-aos="fade-up" data-aos-delay="200">
          <div class="modern-contact-info">
            <h3 class="modern-info-title mb-4">{{ contactInfoHeading }}</h3>
            <p class="info-description">We're here to help you succeed. Get in touch and let's start a conversation.</p>
            
            <div class="contact-items">
              <div class="modern-contact-item">
                <a
                  :href="'https://www.google.com/maps/search/?api=1&query=' + encodeURIComponent(contactInfo.address)"
                  target="_blank"
                  class="modern-contact-link"
                >
                  <div class="contact-icon-wrapper">
                    <span class="icon-room contact-icon"></span>
                  </div>
                  <div class="contact-details">
                    <div class="contact-label">Office</div>
                    <div class="contact-value">{{ contactInfo.address }}</div>
                  </div>
                </a>
              </div>

              <div class="modern-contact-item">
                <a :href="'tel://' + contactInfo.phone1" class="modern-contact-link">
                  <div class="contact-icon-wrapper">
                    <span class="icon-phone contact-icon"></span>
                  </div>
                  <div class="contact-details">
                    <div class="contact-label">Phone</div>
                    <div class="contact-value">{{ contactInfo.phone1 }}</div>
                  </div>
                </a>
              </div>

              <div class="modern-contact-item">
                <a :href="'mailto:' + contactInfo.email" class="modern-contact-link">
                  <div class="contact-icon-wrapper">
                    <span class="icon-envelope contact-icon"></span>
                  </div>
                  <div class="contact-details">
                    <div class="contact-label">Email</div>
                    <div class="contact-value">{{ contactInfo.email }}</div>
                  </div>
                </a>
              </div>

              <div class="modern-contact-item">
                <a :href="contactInfo.website" target="_blank" class="modern-contact-link">
                  <div class="contact-icon-wrapper">
                    <span class="icon-globe contact-icon"></span>
                  </div>
                  <div class="contact-details">
                    <div class="contact-label">Website</div>
                    <div class="contact-value">{{ contactInfo.website }}</div>
                  </div>
                </a>
              </div>
            </div>

            <div class="response-info">
              <h4>Quick Response</h4>
              <p>We typically respond within 24 hours</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.modern-contact-section {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 120px 0;
  position: relative;
}

.modern-contact-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(255, 255, 255, 0.05);
  background-image: radial-gradient(circle at 25% 25%, rgba(255, 255, 255, 0.1) 1px, transparent 1px);
  background-size: 50px 50px;
}

.modern-heading {
  font-size: 3rem;
  font-weight: 700;
  color: white;
  margin-bottom: 1rem;
  letter-spacing: -0.02em;
}

.modern-subheading {
  font-size: 1.2rem;
  color: rgba(255, 255, 255, 0.9);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.7;
}

.modern-form-container {
  background: white;
  border-radius: 24px;
  padding: 48px;
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
  backdrop-filter: blur(10px);
  position: relative;
  z-index: 1;
}

.form-header {
  margin-bottom: 32px;
}

.form-header h3 {
  font-size: 1.5rem;
  font-weight: 600;
  color: #2d3748;
  margin-bottom: 8px;
}

.form-header p {
  color: #718096;
  margin: 0;
  font-size: 1rem;
}

.modern-form-group {
  margin-bottom: 24px;
}

.modern-label {
  display: block;
  margin-bottom: 8px;
  font-weight: 500;
  color: #4a5568;
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.modern-input,
.modern-textarea {
  width: 100%;
  padding: 16px 20px;
  border: 2px solid #e2e8f0;
  border-radius: 12px;
  font-size: 1rem;
  transition: all 0.2s ease;
  background-color: #f7fafc;
  font-family: inherit;
}

.modern-input:focus,
.modern-textarea:focus {
  outline: none;
  border-color: var(--theme-color, #667eea);
  background-color: white;
  box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
}

.modern-textarea {
  resize: vertical;
  min-height: 120px;
}

.modern-btn {
  width: 100%;
  padding: 18px 32px;
  border: none;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  color: white;
}

.modern-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
}

.modern-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
  transform: none;
}

.modern-contact-info {
  color: white;
  position: relative;
  z-index: 1;
}

.modern-info-title {
  font-size: 2rem;
  font-weight: 600;
  color: white;
}

.info-description {
  font-size: 1.1rem;
  line-height: 1.8;
  margin-bottom: 48px;
  color: rgba(255, 255, 255, 0.9);
}

.contact-items {
  margin-bottom: 40px;
}

.modern-contact-item {
  margin-bottom: 24px;
}

.modern-contact-link {
  display: flex;
  align-items: flex-start;
  text-decoration: none;
  color: inherit;
  padding: 20px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.2s ease;
}

.modern-contact-link:hover {
  background: rgba(255, 255, 255, 0.15);
  transform: translateY(-2px);
  text-decoration: none;
  color: inherit;
}

.contact-icon-wrapper {
  width: 24px;
  height: 24px;
  margin-right: 20px;
  margin-top: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.contact-icon {
  color: rgba(255, 255, 255, 0.9);
  font-size: 20px;
}

.contact-details {
  flex: 1;
}

.contact-label {
  font-size: 0.8rem;
  font-weight: 600;
  color: rgba(255, 255, 255, 0.7);
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin-bottom: 4px;
}

.contact-value {
  color: white;
  font-size: 1.1rem;
  line-height: 1.5;
}

.response-info {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  padding: 24px;
  text-align: center;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.response-info h4 {
  color: white;
  font-size: 1.1rem;
  margin-bottom: 8px;
  font-weight: 600;
}

.response-info p {
  color: rgba(255, 255, 255, 0.8);
  margin: 0;
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .modern-contact-section {
    padding: 80px 0;
  }

  .modern-heading {
    font-size: 2.5rem;
  }

  .modern-form-container {
    padding: 32px 24px;
    margin-bottom: 40px;
  }

  .modern-info-title {
    font-size: 1.5rem;
  }
}

@media (max-width: 480px) {
  .modern-heading {
    font-size: 2rem;
  }

  .modern-form-container {
    padding: 24px 20px;
  }
}
</style>
