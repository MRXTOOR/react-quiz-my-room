# react-quiz-my-room [Приложение](https://react-quiz-my-room.vercel.app/)
[![Typing SVG](https://readme-typing-svg.herokuapp.com?color=%2336BCF7&lines=react+quiz+webApp)](https://git.io/typing-svg)
![Desktop 2023 01 03 - 02 18 26 04 (online-video-cutter com) (1)](https://user-images.githubusercontent.com/57110073/210284491-9617245b-dadb-4061-98e3-73967f8631b2.gif)

![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)





<h3 align="center">Веб приложение с вопросами</h3>
<h4>Приложение постороенно на react js</h4>
<h4>В приложении можно отвечать на зараие прописанные вопросы на js </h4>
<h4>Приложение дает возможность отвечать на вопросы из постороенного массива </h4>

```javaScript

const questions = [
  {
    title: 'На чем я пишу эту штуку🔰',
    variants: ['Бумага📃', 'React⚛️', 'Php🐘'],
    correct: 1,
  }
  ];
  
```

<h4>пример массива</h4>

# Реализация

<h4>Реализованно через useState</h4>
<h4>Человек нажимая на слово из ответов в масиве делится на количество ответов умнажая на 100 что показывает прогресс по тесту  </h4>

```javaScript

function Game({step, question,onClickVariant}) {
  // тут лежит статика 
  const percentage = Math.round((step / questions.length) * 100)

  return (
    <>
      <div className="progress">
        <div style={{ width: `${percentage}%` }} className="progress__inner"></div>
      </div>
      <h1>{question.title}</h1>
      <ul>
        {question.variants.map((text,index) =>( 
        <li onClick={() => onClickVariant(index)} key={text}>{text}</li>
          ))}
      </ul>
    </>
  );
}

```

<h4>Код реализации рендрига</h4>


```javaScript
                    function App() {
  const [step, setStep] = React.useState(0);
  const [correct, setCorrect] = React.useState(0);
  const question = questions[step];


  const onClickVariant = (index) => {
    setStep(step + 1);
    if (index === question.correct){
      setCorrect(correct + 1 )
    }
  }
  return (
    <div className="App">
      {
        step !== questions.length ? (<Game step={step} question={question} onClickVariant={onClickVariant}/> 
        ):(
        <Result correct={correct}/>
        )}
      
    </div>
  );
}
```


[Исходный код react проекта](https://github.com/MRXTOOR/react-quiz-app-depl/tree/master/src)
