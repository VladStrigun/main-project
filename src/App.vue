<template>
  <div>
    <header>
      <div>My personal costs</div>
    </header>
    <main>
      <div>
        <button @click="formShow = !formShow" id="form">Add New Cost +</button>

        <div>
          <AddPaymentForm @addNewPayment="addNewPayment" v-show="formShow" />
        </div>
      </div>
      <div><PaymentsDisplay :items="paymentsList" /></div>
    </main>
  </div>
</template>
 
<script>
import PaymentsDisplay from "./components/PaymentsDisplay";
import AddPaymentForm from "./components/AddPaymentForm";

export default {
  components: {
    PaymentsDisplay,
    AddPaymentForm,
  },
  data() {
    return {
      formShow: false,
      paymentsList: [],
    };
  },
  methods: {
    addNewPayment(data) {
      this.paymentsList = [...this.paymentsList, data];
    },
    fetchData() {
      return [
        {
          date: "28.03.2020",
          category: "Food",
          value: 169,
        },
        {
          date: "24.03.2020",
          category: "Transport",
          value: 360,
        },
        {
          date: "24.03.2020",
          category: "Food",
          value: 532,
        },
      ];
    },
  },
  created() {
    this.paymentsList = this.fetchData();
  },
};
</script>
