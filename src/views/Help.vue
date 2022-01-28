<template>
  <app-page title="Помощь">
    <question-item
      v-for="q in questions"
      :key="q.title"
      :question="q"
    ></question-item>
  </app-page>
</template>

<script>
import AppPage from '../components/ui/AppPage.vue'
import QuestionItem from '../components/question/QuestionItem.vue'

export default {
  setup() {
    const questions = [
      {
        title: `Что есть в этом приложении?`,
        text: `В приложении есть два раздела: Заявки и Помощь.
          В первом разделе вы можете создать заявку, а во втором разделе вы можете получить информацию о приложении.`,
      },
      {
        title: `Как создать заявку?`,
        text: `В разделе "Заявки" нажав на кнопку "Создать", вам откроется окно создания заявки.
          Все поля обязательны к заполнению. Вам будет предложено ввести своё ФИО, телефон, сумму денег, и выбрать статус. 
          После этого нажав на кнопку "Создать", появится сообщение с успешной созданной заявкой, которая будет отображена в главном окне.`,
      },
      {
        title: `Как работает авторизация?`,
        text: `Всё реализовано ерез Firebase`,
      },
    ]

    return {
      questions,
    }
  },
  components: {
    AppPage,
    QuestionItem,
  },
}
</script>
