var questions = [
  {
    question: "Haben Sie sich meine Bewerbung gut durchgelesen",
    answers: [
      {text: "Nein"},
      {text: "Ja", isCorrect: true},
      {text: "najaaa"},
    ]
  },
  {
    question: "Sicher?",
    answers: [
      {text: "ja"},
      {text: "Aufjedenfall", isCorrect: true},
      {text: "Solala"},
    ]
  },
  {
    question: "Wie werde ich geschrieben?",
    answers: [
      {text: "Rebecca"},
      {text: "Rebecka", isCorrect: true},
      {text: "Rebekka"},
    ]
  },
  {
    question: "Was studiere ich an der TU?",
    answers: [
      {text: "ITM", isCorrect: true},
      {text: "Maschinenbau"},
      {text: "Informatik"},
    ]
  },
  {
    question: "?",
    answers: [
      {text: "Ottawa", isCorrect: true},
      {text: "Toronto"},
      {text: "Vancouver"},
    ]
  },
  {
    question: "What is the capital of Paraguay?",
    answers: [
      {text: "Asunción", isCorrect: true},
      {text: "La Paz"},
      {text: "Montevideo"},
    ]
  },
  {
    question: "What is the capital of Vietnam?",
    answers: [
      {text: "Hanoi", isCorrect: true},
      {text: "Ho Chi Minh City"},
      {text: "Phnom Penh"},
    ]
  },
  {
    question: "What is the capital of India?",
    answers: [
      {text: "Bangalore"},
      {text: "Bombay"},
      {text: "New Delhi", isCorrect: true},
    ]
  },
  {
    question: "What is the capital of Iraq?",
    answers: [
      {text: "Baghdad", isCorrect: true},
      {text: "Damas"},
      {text: "Tehran"},
    ]
  },
  {
    question: "What is the capital of Colombia?",
    answers: [
      {text: "Bogotá", isCorrect: true},
      {text: "Caracas"},
      {text: "Quito"},
    ]
  },
];
var score = 0;
var iQuestion = 0;

function updateQuestionAndScore() {
  if (iQuestion >= questions.length) {
    document.getElementsByClassName('question')[0].outerHTML = '';
    document.getElementsByClassName('answer')[2].outerHTML = '';
    document.getElementsByClassName('answer')[1].outerHTML = '';
    document.getElementsByClassName('answer')[0].outerHTML = '';
    return;
  }
  document.getElementsByClassName('score')[0].innerHTML = score;  
  document.getElementsByClassName('question')[0].innerHTML = questions[iQuestion].question;
  var answers = document.getElementsByClassName('answer');
  for (let i = 0; i < answers.length; i++) {
    answers[i].innerHTML = questions[iQuestion].answers[i].text;
  }
}

document.addEventListener("DOMContentLoaded", function(event) { 
  var answers = document.getElementsByClassName('answer');
  for (let i = 0; i < answers.length; i++) {
    answers[i].onclick = function() {
      if (questions[iQuestion].answers[i].isCorrect) {
        score++;
      }
      iQuestion++;
      updateQuestionAndScore();
    }
  }
  updateQuestionAndScore();
});
