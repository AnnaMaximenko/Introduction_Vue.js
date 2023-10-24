<!-- Вам необходимо создать компонент ипотечного калькулятора,
который позволяет пользователю вводить сумму кредита, процентную ставку и срок
кредита. Компонент должен автоматически вычислять ежемесячный платеж и общую
сумму выплаты по кредиту.

Создайте компонент MortgageCalculator
с соответствующим шаблоном и скриптом. В шаблоне компонента разместите поля
ввода для суммы кредита, процентной ставки и срока кредита, а также элементы для
отображения ежемесячного платежа и общей суммы выплаты. Используйте директиву
v-model для связывания введенных пользователем значений с соответствующими
свойствами в компоненте. Создайте вычисляемое свойство monthlyPayment, которое
будет вычислять ежемесячный платеж на основе введенных значений суммы кредита,
процентной ставки и срока кредита. Создайте вычисляемое свойство totalPayment,
которое будет вычислять общую сумму выплаты по кредиту, учитывая ежемесячный
платеж и срок кредита. Отобразите значения monthlyPayment и totalPayment в
соответствующих элементах шаблона. -->

<template>
  <div>
    <form>
      <input
        v-model.number="credit"
        type="number"
        placeholder="Сумма
      кредита"
      />
      <input
        v-model.number="percent"
        type="number"
        placeholder="Процентная ставка"
      />
      <input v-model.number="period" type="number" placeholder="Срок кредита" />
    </form>
    <h2>Ежемесячный платеж - {{ payment.payByMonth }}</h2>
    <h2>Общая сумма кредита - {{ payment.total }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      credit: null,
      percent: null,
      period: null,
    };
  },
  computed: {
    payment() {
      const principal = parseFloat(this.credit);
      const interestRate = parseFloat(this.percent) / 100 / 12;
      const loanTermMonths = parseFloat(this.period) * 12;

      const numerator =
        principal * interestRate * Math.pow(1 + interestRate, loanTermMonths);
      const denominator = Math.pow(1 + interestRate, loanTermMonths) - 1;
      const payByMonth = (numerator / denominator).toFixed(2);
      const total = (payByMonth * 12 * this.period).toFixed(2);
      return { payByMonth, total };
    },
  },
};
</script>

<style lang="scss" scoped></style>
