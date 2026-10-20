<script>
import About from './components/About.vue';
import Booking from './components/Booking.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
import Herosection from './components/Herosection.vue';
import Modal from './components/Modal.vue';
import Nav from './components/Nav.vue';
import Transaction from './components/Transaction.vue';

export default {
  components: {
    Nav,
    Herosection,
    About,
    Contact,
    Footer,
    Modal,
    Booking,
    Transaction
  },
  data() {
    return {
      modal: false,
      currentPage: 'Home',
      appointment: [],
      transactions: []
    }
  },
  methods: {
    modalAct(mod) {
      this.modal = mod;
    },
    closeModal(mod) {
      this.modal = mod;
    },
    NavAction(page){
      this.currentPage = page;
    },
    receiveForm(id, name, email, phone, select, doc, mdy, oras, message){
      this.appointment.push({...id, ...name, ...email, ...phone, ...select, ...doc, ...mdy, ...oras, ...message})
    },
    receiveComplete(id, name, email,  phone, select, doc, mdy, oras, message){
      this.transactions.push({...id, ...name, ...email, ...phone, ...select, ...doc, ...mdy, ...oras, ...message})
    },
    scrollTop(){
      window.scrollTo({
        top:0,
        behavior: 'auto'
      })
    }
  }
}
</script>

<template>
  <Modal v-if="modal == true" @modal="closeModal" @send-to="receiveForm" />
  <Nav @showModal="modalAct" @goTo="NavAction" @click="scrollTop"/>
  <Herosection v-if="currentPage === 'Home'"/>
  <About v-if="currentPage === 'Home'"/>
  <Contact v-if="currentPage === 'Home'"/>
  <Booking v-if="currentPage === 'Booking' " @complete="receiveComplete" :sendForm="this.appointment"/>
  <Transaction v-if="currentPage === 'Transaction'"  :sendComplete="this.transactions"/>

  <Footer />
</template>
