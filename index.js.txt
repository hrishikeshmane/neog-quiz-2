const readlineSync = require("readline-sync")
let score = 0;
let level = 1;
let highScore = 5;
const questions = [
  {
    q: `Which of the following is a lawyer by profession?
    a: She Hulk
    b: Batgirl
    c: Raven
    Your answer: `,
    a: "a"
  },
  {
    q: `Which of the following is a Teen Titan Character?
    a: Superman
    b: Shazam
    c: Robin 
    Your answer: `,
    a: "c"
  },
  {
    q: `Which of the following is a weekness of Superman?
    a: Orb
    b: Krypton
    c: Lex Luther 
    Your answer: `,
    a: "b"
  },
  {
    q: `Which of the following is a DC villan?
    a: Darth Wader
    b: Thanos
    c: Dark Seid 
    Your answer: `,
    a: "c"
  },
  {
    q: `Which of the following is a magical charater?
    a: Dr Strange
    b: Hulk
    c: Punisher 
    Your answer: `,
    a: "a"
  },
  {
    q: `Which of the following is a blind charater?
    a: Dr Doom
    b: Daredevil
    c: Goblin 
    Your answer: `,
    a: "b"
  }
]

const game = (question, answer) => {
  const userInput = readlineSync.question(question);

  if (userInput.toLowerCase() === answer.toLowerCase()) {
    score = score + 1;
  } else {
    score = score - 1;
  } 
}

const name = readlineSync.question("Hi, What is your name? ");

console.log(`Hello ${name}, Lets see how well you know your friend.`);
console.log("-------------------");

questions.forEach(entry => {
  game(entry.q, entry.a);
})

console.log("-------------------");
console.log(`Your final score is ${score}`)