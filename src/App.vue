<template>
  <div class="invitation-app">
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-content">
        <div class="logo-container">
          <img src="/ES-CIRC.png" alt="esTODOMADERA..." class="logo-image">
        </div>
        
        <div class="event-info">
          <h2 class="event-title">Gran Inauguración</h2>
          <p class="event-date">{{ eventData.date }}</p>
          <p class="event-time">{{ eventData.time }}</p>
        </div>

        <button @click="scrollToSection('detalles')" class="cta-button">
          Ver Detalles
        </button>
      </div>
      
      <div class="scroll-indicator">
        <span>Desliza hacia abajo</span>
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
          <path d="M12 5V19M12 19L5 12M12 19L19 12" stroke="currentColor" stroke-width="2"/>
        </svg>
      </div>
    <!-- </section> -->
      
      <div class="scroll-indicator">
        <span>Desliza hacia abajo</span>
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
          <path d="M12 5V19M12 19L5 12M12 19L19 12" stroke="currentColor" stroke-width="2"/>
        </svg>
      </div>
    </section>

    <!-- Mensaje Personal -->
    <section id="mensaje" class="section message-section">
      <div class="container">
        <div class="section-content">
          <div class="decorative-icon">
            <svg width="60" height="60" viewBox="0 0 60 60" fill="none">
              <rect x="10" y="5" width="8" height="50" fill="currentColor"/>
              <rect x="22" y="5" width="8" height="50" fill="currentColor"/>
              <rect x="34" y="5" width="8" height="50" fill="currentColor"/>
              <rect x="46" y="5" width="8" height="50" fill="currentColor"/>
            </svg>
          </div>
          <h2 class="section-title">{{ eventData.title }}</h2>
          <p class="message-text">{{ eventData.message }}</p>
        </div>
      </div>
    </section>

    <!-- Detalles del Evento -->
    <section id="detalles" class="section details-section">
      <div class="container">
        <h2 class="section-title">Detalles del Evento</h2>
        
        <div class="details-grid">
          <div class="detail-card">
            <div class="detail-icon">
              <svg width="40" height="40" viewBox="0 0 24 24" fill="none">
                <rect x="3" y="4" width="18" height="18" rx="2" stroke="currentColor" stroke-width="2"/>
                <path d="M3 10H21M8 2V6M16 2V6" stroke="currentColor" stroke-width="2"/>
              </svg>
            </div>
            <h3>Fecha</h3>
            <p>{{ eventData.date }}</p>
          </div>

          <div class="detail-card">
            <div class="detail-icon">
              <svg width="40" height="40" viewBox="0 0 24 24" fill="none">
                <circle cx="12" cy="12" r="9" stroke="currentColor" stroke-width="2"/>
                <path d="M12 6V12L16 14" stroke="currentColor" stroke-width="2"/>
              </svg>
            </div>
            <h3>Hora</h3>
            <p>{{ eventData.time }}</p>
          </div>

          <div class="detail-card">
            <div class="detail-icon">
              <svg width="40" height="40" viewBox="0 0 24 24" fill="none">
                <path d="M21 10C21 17 12 23 12 23C12 23 3 17 3 10C3 5.02944 7.02944 1 12 1C16.9706 1 21 5.02944 21 10Z" stroke="currentColor" stroke-width="2"/>
                <circle cx="12" cy="10" r="3" stroke="currentColor" stroke-width="2"/>
              </svg>
            </div>
            <h3>Ubicación</h3>
            <p>{{ eventData.location }}</p>
            <button @click="openLocation" class="action-button">
              Ver en Mapa
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Dress Code -->
    <section id="dress-code" class="section dress-code-section">
      <div class="container">
        <h2 class="section-title">Dress Code</h2>
        <div class="dress-code-content">
          <div class="dress-icon">
            <svg width="80" height="80" viewBox="0 0 24 24" fill="none">
              <path d="M16 3L20 7V21H4V7L8 3H16Z" stroke="currentColor" stroke-width="2"/>
              <path d="M12 3V8" stroke="currentColor" stroke-width="2"/>
              <path d="M8 3L6 7M16 3L18 7" stroke="currentColor" stroke-width="2"/>
            </svg>
          </div>
          <h3>{{ eventData.dressCode.style }}</h3>
          <p>{{ eventData.dressCode.description }}</p>
          <div class="color-palette">
            <div 
              v-for="(color, index) in eventData.dressCode.colors" 
              :key="index"
              class="color-swatch"
              :style="{ backgroundColor: color }"
              :title="color"
            ></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Mesa de Regalos -->
    <section id="regalos" class="section gifts-section">
      <div class="container">
        <h2 class="section-title">Mesa de Regalos</h2>
        <div class="gifts-content">
          <div class="gift-icon">
            <svg width="80" height="80" viewBox="0 0 24 24" fill="none">
              <rect x="3" y="10" width="18" height="11" stroke="currentColor" stroke-width="2"/>
              <path d="M3 10V7C3 5.89543 3.89543 5 5 5H19C20.1046 5 21 5.89543 21 7V10" stroke="currentColor" stroke-width="2"/>
              <path d="M12 5V21" stroke="currentColor" stroke-width="2"/>
              <path d="M12 5C12 3.34315 10.6569 2 9 2C7.34315 2 6 3.34315 6 5C6 5 7.5 5 9 5H12Z" stroke="currentColor" stroke-width="2"/>
              <path d="M12 5C12 3.34315 13.3431 2 15 2C16.6569 2 18 3.34315 18 5C18 5 16.5 5 15 5H12Z" stroke="currentColor" stroke-width="2"/>
            </svg>
          </div>
          <p class="gifts-text">{{ eventData.gifts.message }}</p>
          
          <div class="gift-options">
            <div 
              v-for="(gift, index) in eventData.gifts.options"
              :key="index"
              class="gift-option"
            >
              <h4>{{ gift.name }}</h4>
              <p>{{ gift.description }}</p>
              <button 
                v-if="gift.link" 
                @click="openLink(gift.link)"
                class="action-button"
              >
                {{ gift.buttonText }}
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Confirmación -->
    <section id="confirmacion" class="section confirmation-section">
      <div class="container">
        <h2 class="section-title">Confirma tu Asistencia</h2>
        <div class="confirmation-content">
          <p class="confirmation-text">{{ eventData.confirmation.message }}</p>
          <p class="confirmation-deadline">Confirma antes del: {{ eventData.confirmation.deadline }}</p>
          
          <div class="confirmation-buttons">
            <button 
              @click="confirmAttendance(true)" 
              class="confirm-button confirm-yes"
              :class="{ active: attendance === true }"
            >
              Asistiré
            </button>
            <button 
              @click="confirmAttendance(false)" 
              class="confirm-button confirm-no"
              :class="{ active: attendance === false }"
            >
              No podré asistir
            </button>
          </div>

          <div v-if="attendance !== null" class="contact-options">
            <p>Confirma por:</p>
            <div class="contact-buttons">
              <button @click="sendWhatsApp" class="contact-button whatsapp">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/>
                </svg>
                WhatsApp
              </button>
              <button @click="sendEmail" class="contact-button email">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                  <rect x="3" y="5" width="18" height="14" rx="2" stroke="currentColor" stroke-width="2"/>
                  <path d="M3 7L12 13L21 7" stroke="currentColor" stroke-width="2"/>
                </svg>
                Email
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="logo-container">
            <img src="/ES-CIRC.png" alt="esTODOMADERA..." class="logo-image">
          </div>
          <div class="footer-links">
            <a :href="eventData.website" target="_blank" rel="noopener">
              Visita nuestra tienda
            </a>
          </div>
        </div>
      </div>
    </footer>

    <!-- Modal de confirmación -->
    <div v-if="showConfirmModal" class="modal-overlay" @click="showConfirmModal = false">
      <div class="modal-content" @click.stop>
        <h3>{{ modalMessage }}</h3>
        <button @click="showConfirmModal = false" class="close-modal">Cerrar</button>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup() {
    const attendance = ref(null)
    const showConfirmModal = ref(false)
    const modalMessage = ref('')

    // Datos del evento - PERSONALIZA ESTOS DATOS
    const eventData = ref({
      title: '¡Nos complace invitarte!',
      message: 'Es un honor para nosotros invitarte a la inauguración de esTODOMADERA... Celebremos juntos este nuevo comienzo y descubre nuestra exclusiva colección de estanterías comerciales de alta calidad.',
      date: 'Sábado 18 de Octubre, 2025',
      time: '18:00 hrs',
      location: 'Santiago del Estero, Argentina',
      locationUrl: 'https://maps.app.goo.gl/M3YdBh1ESA9cU5PZ9', // PERSONALIZAR CON DIRECCIÓN EXACTA
      dressCode: {
        style: 'Elegante Casual',
        description: 'Sugerimos tonos neutros y elegantes que reflejen la calidez de la madera',
        colors: ['#2c1810', '#8b6f47', '#d4a574', '#f5f1ed']
      },
      gifts: {
        message: 'Tu presencia es nuestro mejor regalo. Si deseas obsequiarnos algo, estas son algunas sugerencias:',
        options: [
          {
            name: 'Transferencia',
            description: 'Alias: estodomadera',
            buttonText: 'Copiar Alias',
            link: null
          },
          {
            name: 'Mesa de Regalos',
            description: 'Visita nuestra tienda online',
            buttonText: 'Ver Tienda',
            link: 'https://es-todo-madera-tienda.vercel.app/'
          }
        ]
      },
      confirmation: {
        message: 'Por favor confirma tu asistencia para que podamos preparar todo con anticipación.',
        deadline: '10 de Octubre, 2025',
        whatsapp: '+5493854864263', // PERSONALIZAR CON NÚMERO REAL
        email: 'Estodomadera@gmail.com' // PERSONALIZAR CON EMAIL REAL
      },
      website: 'https://es-todo-madera-tienda.vercel.app/'
    })

    const scrollToSection = (sectionId) => {
      const element = document.getElementById(sectionId)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'start' })
      }
    }

    const openLocation = () => {
      window.open(eventData.value.locationUrl, '_blank')
    }

    const openLink = (url) => {
      if (url) {
        window.open(url, '_blank')
      } else {
        // Copiar alias al portapapeles
        navigator.clipboard.writeText('estodomadera')
        modalMessage.value = '¡Alias copiado al portapapeles!'
        showConfirmModal.value = true
      }
    }

    const confirmAttendance = (attending) => {
      attendance.value = attending
      modalMessage.value = attending 
        ? '¡Gracias por confirmar! Esperamos verte en el evento.' 
        : 'Lamentamos que no puedas asistir. ¡Gracias por avisar!'
      showConfirmModal.value = true
    }

    const sendWhatsApp = () => {
      const message = attendance.value
        ? 'Hola! Confirmo mi asistencia al evento de esTODOMADERA...'
        : 'Hola! Lamentablemente no podré asistir al evento de esTODOMADERA...'
      const url = `https://wa.me/${eventData.value.confirmation.whatsapp.replace(/\+/g, '')}?text=${encodeURIComponent(message)}`
      window.open(url, '_blank')
    }

    const sendEmail = () => {
      const subject = 'Confirmación de asistencia - esTODOMADERA...'
      const body = attendance.value 
        ? 'Hola! Confirmo mi asistencia al evento de inauguración.'
        : 'Hola! Lamentablemente no podré asistir al evento de inauguración.'
      const url = `mailto:${eventData.value.confirmation.email}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`
      window.location.href = url
    }

    return {
      eventData,
      attendance,
      showConfirmModal,
      modalMessage,
      scrollToSection,
      openLocation,
      openLink,
      confirmAttendance,
      sendWhatsApp,
      sendEmail
    }
  }
}
</script>

<style scoped>
/* Hero Section */
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #1a1a1a 0%, #2c1810 100%);
  color: var(--color-white);
  position: relative;
  padding: 40px 20px;
}

.hero-content {
  text-align: center;
  z-index: 2;
}

.circle-border {
  width: 350px;
  height: 350px;
  border: 8px solid var(--color-accent);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 40px;
  position: relative;
  animation: fadeInScale 1s ease-out;
}

@keyframes fadeInScale {
  from {
    opacity: 0;
    transform: scale(0.8);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

.logo-container {
  text-align: center;
  padding: 40px;
}

.brand-name {
  font-family: var(--font-heading);
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 10px;
  letter-spacing: 2px;
}

.tagline {
  font-family: var(--font-body);
  font-size: 1.2rem;
  font-weight: 300;
  letter-spacing: 3px;
  color: var(--color-accent);
}

.event-info {
  margin: 40px 0;
  animation: fadeInUp 1s ease-out 0.3s both;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.event-title {
  font-family: var(--font-heading);
  font-size: 2.5rem;
  margin-bottom: 20px;
  color: var(--color-accent);
}

.event-date,
.event-time {
  font-size: 1.3rem;
  margin: 10px 0;
  font-weight: 300;
}

.cta-button {
  margin-top: 40px;
  padding: 18px 50px;
  font-size: 1.1rem;
  font-weight: 600;
  background: var(--color-accent);
  color: var(--color-primary);
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-family: var(--font-body);
  letter-spacing: 1px;
  animation: fadeInUp 1s ease-out 0.6s both;
}

.cta-button:hover {
  background: var(--color-white);
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(212, 165, 116, 0.3);
}

.scroll-indicator {
  position: absolute;
  bottom: 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  color: var(--color-accent);
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(10px); }
}

/* Sections */
.section {
  padding: 100px 20px;
  position: relative;
}

.section:nth-child(even) {
  background-color: var(--color-white);
}

.section-title {
  font-family: var(--font-heading);
  font-size: 3rem;
  text-align: center;
  margin-bottom: 60px;
  color: var(--color-primary);
  position: relative;
}

.section-title::after {
  content: '';
  display: block;
  width: 100px;
  height: 3px;
  background: var(--color-accent);
  margin: 20px auto 0;
}

/* Message Section */
.message-section {
  background: linear-gradient(135deg, var(--color-light) 0%, var(--color-white) 100%);
}

.section-content {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.decorative-icon {
  color: var(--color-accent);
  margin-bottom: 30px;
}

.message-text {
  font-size: 1.3rem;
  line-height: 1.8;
  color: var(--color-primary);
  font-weight: 300;
}

/* Details Section */
.details-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 40px;
  max-width: 1000px;
  margin: 0 auto;
}

.detail-card {
  background: var(--color-white);
  padding: 40px 30px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.detail-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
}

.detail-icon {
  color: var(--color-accent);
  margin-bottom: 20px;
}

.detail-card h3 {
  font-family: var(--font-heading);
  font-size: 1.8rem;
  margin-bottom: 15px;
  color: var(--color-primary);
}

.detail-card p {
  font-size: 1.1rem;
  color: var(--color-secondary);
  margin-bottom: 20px;
}

.action-button {
  padding: 12px 30px;
  background: var(--color-primary);
  color: var(--color-white);
  border: none;
  border-radius: 25px;
  cursor: pointer;
  font-weight: 500;
  transition: all 0.3s ease;
  font-family: var(--font-body);
}

.action-button:hover {
  background: var(--color-accent);
  color: var(--color-primary);
  transform: scale(1.05);
}

/* Dress Code Section */
.dress-code-content {
  max-width: 600px;
  margin: 0 auto;
  text-align: center;
}

.dress-icon {
  color: var(--color-accent);
  margin-bottom: 30px;
}

.dress-code-content h3 {
  font-family: var(--font-heading);
  font-size: 2rem;
  margin-bottom: 20px;
  color: var(--color-primary);
}

.dress-code-content p {
  font-size: 1.2rem;
  line-height: 1.6;
  margin-bottom: 30px;
  color: var(--color-secondary);
}

.color-palette {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 30px;
}

.color-swatch {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  border: 3px solid var(--color-white);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease;
}

.color-swatch:hover {
  transform: scale(1.2);
}

/* Gifts Section */
.gifts-content {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.gift-icon {
  color: var(--color-accent);
  margin-bottom: 30px;
}

.gifts-text {
  font-size: 1.2rem;
  margin-bottom: 40px;
  color: var(--color-secondary);
}

.gift-options {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
  margin-top: 40px;
}

.gift-option {
  background: var(--color-light);
  padding: 30px;
  border-radius: 15px;
  transition: all 0.3s ease;
}

.gift-option:hover {
  background: var(--color-white);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.gift-option h4 {
  font-family: var(--font-heading);
  font-size: 1.5rem;
  margin-bottom: 15px;
  color: var(--color-primary);
}

.gift-option p {
  font-size: 1.1rem;
  margin-bottom: 20px;
  color: var(--color-secondary);
}

/* Confirmation Section */
.confirmation-content {
  max-width: 600px;
  margin: 0 auto;
  text-align: center;
}

.confirmation-text {
  font-size: 1.2rem;
  margin-bottom: 20px;
  color: var(--color-secondary);
}

.confirmation-deadline {
  font-size: 1.1rem;
  margin-bottom: 40px;
  color: var(--color-accent);
  font-weight: 600;
}

.confirmation-buttons {
  display: flex;
  gap: 20px;
  justify-content: center;
  margin-bottom: 40px;
  flex-wrap: wrap;
}

.confirm-button {
  padding: 18px 40px;
  font-size: 1.1rem;
  font-weight: 600;
  border: 2px solid var(--color-primary);
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-family: var(--font-body);
  background: transparent;
  color: var(--color-primary);
}

.confirm-button:hover,
.confirm-button.active {
  background: var(--color-primary);
  color: var(--color-white);
  transform: scale(1.05);
}

.confirm-yes.active {
  background: #4CAF50;
  border-color: #4CAF50;
  color: white;
}

.confirm-no.active {
  background: #f44336;
  border-color: #f44336;
  color: white;
}

.contact-options {
  margin-top: 40px;
  padding-top: 40px;
  border-top: 2px solid var(--color-light);
}

.contact-options p {
  font-size: 1.2rem;
  margin-bottom: 20px;
  color: var(--color-primary);
}

.contact-buttons {
  display: flex;
  gap: 20px;
  justify-content: center;
  flex-wrap: wrap;
}

.contact-button {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 15px 35px;
  font-size: 1.1rem;
  font-weight: 600;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-family: var(--font-body);
}

.whatsapp {
  background: #25D366;
  color: white;
}

.whatsapp:hover {
  background: #20BA5A;
  transform: scale(1.05);
}

.email {
  background: var(--color-primary);
  color: white;
}

.email:hover {
  background: var(--color-secondary);
  transform: scale(1.05);
}

/* Footer */
.footer {
  background: var(--color-primary);
  color: var(--color-white);
  padding: 60px 20px 40px;
  text-align: center;
}

.footer-content {
  max-width: 600px;
  margin: 0 auto;
}

.circle-border-small {
  width: 150px;
  height: 150px;
  border: 4px solid var(--color-accent);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 30px;
}

.footer-brand {
  font-family: var(--font-heading);
  font-size: 1.3rem;
  font-weight: 700;
  letter-spacing: 1px;
}

.footer-text {
  font-size: 1rem;
  margin-bottom: 30px;
  color: var(--color-accent);
}

.footer-links a {
  color: var(--color-accent);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: var(--color-white);
}

/* Modal */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  padding: 20px;
}

.modal-content {
  background: white;
  padding: 40px;
  border-radius: 20px;
  max-width: 500px;
  width: 100%;
  text-align: center;
  animation: modalAppear 0.3s ease-out;
}

@keyframes modalAppear {
  from {
    opacity: 0;
    transform: scale(0.8);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

.modal-content h3 {
  font-family: var(--font-heading);
  font-size: 1.8rem;
  margin-bottom: 30px;
  color: var(--color-primary);
}

.close-modal {
  padding: 12px 40px;
  background: var(--color-accent);
  color: var(--color-primary);
  border: none;
  border-radius: 25px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  font-family: var(--font-body);
}

.close-modal:hover {
  background: var(--color-primary);
  color: white;
}

/* Responsive */
@media (max-width: 768px) {
  .hero {
    padding: 60px 20px;
  }

  .circle-border {
    width: 280px;
    height: 280px;
    border-width: 6px;
  }

  .brand-name {
    font-size: 2rem;
  }

  .tagline {
    font-size: 1rem;
  }

  .event-title {
    font-size: 2rem;
  }

  .event-date,
  .event-time {
    font-size: 1.1rem;
  }

  .section {
    padding: 60px 20px;
  }

  .section-title {
    font-size: 2rem;
  }

  .message-text {
    font-size: 1.1rem;
  }

  .details-grid {
    grid-template-columns: 1fr;
  }

  .confirmation-buttons {
    flex-direction: column;
  }

  .confirm-button {
    width: 100%;
  }

  .contact-buttons {
    flex-direction: column;
  }

  .contact-button {
    width: 100%;
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .circle-border {
    width: 240px;
    height: 240px;
  }

  .brand-name {
    font-size: 1.6rem;
  }

  .cta-button {
    padding: 15px 35px;
    font-size: 1rem;
  }
}
</style>
