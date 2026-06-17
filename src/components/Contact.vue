<template>
  <section id="Contact" class="contact-section">
    <h2>Contact Me</h2>
    <p class="subtitle">Let’s work together 🚀</p>

    <div class="contact-container">
      
      <div class="contact-info">
        <div class="socials-list">
          <a href="mailto:kmhlakane@gmail.com" class="social-item email">
            <i class="fa-solid fa-envelope"></i>
            <span>kmhlakane@gmail.com</span>
          </a>

          <a href="tel:0833946726" class="social-item phone">
            <i class="fa-solid fa-mobile-screen-button"></i>
            <span>083 394 6726</span>
          </a>

          <a href="https://github.com/Khangelan" target="_blank" class="social-item github">
            <i class="fa-brands fa-github"></i>
            <span>GitHub</span>
          </a>
          
          <a href="https://www.linkedin.com/in/khangelani-mhlakane-689638401/" target="_blank" class="social-item linkedin">
            <i class="fa-brands fa-linkedin"></i>
            <span>LinkedIn</span>
          </a>

          <a href="https://wa.me/27833946726" target="_blank" class="social-item whatsapp">
            <i class="fa-brands fa-whatsapp"></i>
            <span>WhatsApp</span>
          </a>
        </div>
      </div>

      <form class="contact-form" @submit.prevent="sendEmail">
        <input type="text" v-model="name" placeholder="Your Name" required />
        <input type="email" v-model="email" placeholder="Your Email" required />
        <textarea v-model="message" placeholder="Your Message" required></textarea>
        <button type="submit">
          {{ loading ? "Sending..." : "🚀 Send Message" }}
        </button>
      </form>

    </div>
  </section>
</template>

<script>
import emailjs from '@emailjs/browser'

export default {
  data() {
    return {
      name: "",
      email: "",
      message: "",
      loading: false
    };
  },
  mounted() {
    emailjs.init("iudlMU3o8cTgWyRRe");
  },
  methods: {
    async sendEmail() {
      this.loading = true;

      const templateParams = {
        name: this.name,
        email: this.email,
        message: this.message
      };

      const serviceID = "service_4k2kjem";
      const templateID = "template_0o68jh9";
      const publicKey = "iudIMU3o8cTgWyRRe";

      try {
        const result = await emailjs.send(serviceID, templateID, templateParams, publicKey);
        console.log("EmailJS success:", result);

        alert("✅ Message sent successfully!");
        this.name = "";
        this.email = "";
        this.message = "";
      } catch (error) {
        console.error("EmailJS send error:", error);
        const errorText = error?.text || error?.message || "Please verify your EmailJS IDs and public key.";
        alert(`❌ Failed to send message: ${errorText}`);
      } finally {
        this.loading = false;
      }
    }
  }
};
</script>

<style scoped>
/* ==========================================================================
   1. MAIN CONTAINER & SECTION STRUCTURE
   ========================================================================== */
.contact-section {
  padding: 80px 20px;
  color: white;
}

.contact-section h2 {
  font-size: 32px;
  margin-bottom: 10px;
}

.subtitle {
  margin-bottom: 40px;
  opacity: 0.7;
}

/* Forces side-by-side desktop alignment */
.contact-container {
  display: flex;
  flex-direction: row; 
  align-items: center; 
  justify-content: space-between; 
  gap: 50px; 
  max-width: 1100px;
  width: 100%;
  margin: 40px auto 0 auto;
}

/* ==========================================================================
   2. LEFT SIDE LAYOUT (Social links & info)
   ========================================================================== */
.contact-info {
  flex: 1;
  min-width: 320px;
  text-align: left;
  display: flex;
  flex-direction: column;
}

.socials-list {
  display: flex;
  flex-direction: column;
  gap: 20px; 
}

.social-item {
  display: inline-flex;
  align-items: center;
  gap: 14px; 
  font-size: 16px;
  font-weight: 500;
  color: #ccd6f6; 
  text-decoration: none;
  transition: all 0.3s ease;
  width: fit-content;
}

.social-item i {
  font-size: 22px;
  width: 25px; 
  text-align: center;
  transition: transform 0.3s ease;
}

/* Hover effects */
.social-item:hover {
  text-decoration: none;
  transform: translateX(5px); 
}

.social-item:hover i {
  transform: scale(1.15); 
}

/* Individual Brand Colors on Hover */
.social-item.email:hover { color: #3b82f6; }
.social-item.phone:hover { color: #60a5fa; }
.social-item.github:hover { color: #ffffff; }
.social-item.linkedin:hover { color: #0077b5; }
.social-item.whatsapp:hover { color: #25d366; }

/* ==========================================================================
   3. RIGHT SIDE LAYOUT (Glassmorphic form)
   ========================================================================== */
.contact-form {
  flex: 1.2;
  min-width: 320px;
  display: flex;
  flex-direction: column; 

  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px); 
  padding: 30px;
  border-radius: 20px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-sizing: border-box; 
}

.contact-form input,
.contact-form textarea {
  width: 100%; 
  margin-bottom: 15px;
  padding: 12px;
  border-radius: 10px;
  border: 1px solid transparent;
  outline: none;
  background: rgba(255, 255, 255, 0.08);
  color: white;
  font-family: inherit;
  box-sizing: border-box;
  transition: all 0.3s ease;
}

.contact-form textarea {
  min-height: 120px;
  resize: vertical; 
}

/* 🔥 FOCUS EFFECT */
.contact-form input:focus,
.contact-form textarea:focus {
  background: rgba(255, 255, 255, 0.12);
  border: 1px solid #3b82f6;
  box-shadow: 0 0 10px rgba(59, 130, 246, 0.5);
}

/* BUTTON */
.contact-form button {
  width: 100%; 
  padding: 12px;
  border: none;
  background: #3b82f6;
  color: white;
  font-weight: bold;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.contact-form button:hover {
  transform: scale(1.02);
  background: #2563eb;
  box-shadow: 0 10px 25px rgba(59, 130, 246, 0.4);
}

/* ==========================================================================
   4. RESPONSIVE MEDIA BREAKPOINT (Mobile & Tablet setup)
   ========================================================================== */
@media (max-width: 850px) {
  .contact-container {
    flex-direction: column; 
    align-items: stretch; 
    gap: 40px;
  }

  .contact-info {
    text-align: left; 
    align-items: flex-start;
    min-width: 280px;
  }
  
  .contact-form {
    min-width: 280px;
  }
}
</style>