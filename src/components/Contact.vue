<template>
  <section id="Contact" class="contact-section">
    <h2>Contact Me</h2>
    <p class="subtitle">Let’s work together 🚀</p>

    <div class="contact-container">
      
      <!-- LEFT SIDE: CONTACT INFO -->
      <div class="contact-info">
        <p>📧 <a href="mailto:kmhlakane@gmail.com">kmhlakane@gmail.com</a></p>
        <p>📱 <a href="tel:0833946726">083 394 6726</a></p>

        <div class="socials">
          <a href="https://github.com/Khangelan" target="_blank">💻 GitHub</a>
          <a href="https://linkedin.com/in/khangelani-mhlakane" target="_blank">🔗 LinkedIn</a>
        </div>

        <!-- WhatsApp -->
        <a 
          href="https://wa.me/27833946726" 
          target="_blank" 
          class="whatsapp-btn"
        >
          💬 Chat on WhatsApp
        </a>
      </div>

      <!-- RIGHT SIDE: CONTACT FORM -->
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
.contact-section {
  padding: 80px 20px;
  color: white;
}

/* Title */
.contact-section h2 {
  font-size: 32px;
  margin-bottom: 10px;
}

.subtitle {
  margin-bottom: 40px;
  opacity: 0.7;
}

/* Container */
.contact-container {
  display: flex;
  gap: 40px;
  flex-wrap: wrap;
  justify-content: center;
  max-width: 1100px;
  margin: auto;
}

/* LEFT SIDE */
.contact-info {
  flex: 1;
  min-width: 280px;
  text-align: left;
}

.contact-info p {
  margin: 12px 0;
  font-size: 15px;
}

/* LINKS */
a {
  color: #3b82f6;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

/* SOCIALS */
.socials {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

/* WHATSAPP BUTTON */
.whatsapp-btn {
  display: inline-block;
  margin-top: 20px;
  padding: 12px 20px;
  background: #25D366;
  border-radius: 30px;
  font-weight: bold;
  transition: 0.3s;
}

.whatsapp-btn:hover {
  transform: scale(1.05);
  background: #1ebe5d;
}

/* FORM (GLASS EFFECT 🔥) */
.contact-form {
  flex: 1;
  min-width: 280px;
  display: flex;
  flex-direction: column;

  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(12px);
  padding: 25px;
  border-radius: 20px;
  border: 1px solid rgba(255,255,255,0.1);
}

/* INPUTS */
.contact-form input,
.contact-form textarea {
  margin-bottom: 15px;
  padding: 12px;
  border-radius: 10px;
  border: 1px solid transparent;
  outline: none;
  background: rgba(255,255,255,0.08);
  color: white;
  transition: 0.3s;
}

/* 🔥 FOCUS EFFECT */
.contact-form input:focus,
.contact-form textarea:focus {
  border: 1px solid #3b82f6;
  box-shadow: 0 0 10px rgba(59, 130, 246, 0.5);
}

/* BUTTON */
.contact-form button {
  padding: 12px;
  border: none;
  background: #3b82f6;
  color: white;
  font-weight: bold;
  border-radius: 30px;
  cursor: pointer;
  transition: 0.3s;
}

.contact-form button:hover {
  transform: scale(1.05);
  background: #2563eb;
  box-shadow: 0 10px 25px rgba(59, 130, 246, 0.4);
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .contact-container {
    flex-direction: column;
  }

  .contact-info {
    text-align: center;
  }
}
</style>