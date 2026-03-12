<!DOCTYPE html>
<html>
<head>
<title>Pharma Quiz Arena</title>

<style>

body{
font-family: Arial;
background:#f4f4f4;
text-align:center;
}

.quiz-box{
background:white;
padding:20px;
width:400px;
margin:auto;
margin-top:100px;
border-radius:10px;
box-shadow:0px 0px 10px gray;
}

button{
display:block;
margin:10px auto;
padding:10px;
width:200px;
font-size:16px;
cursor:pointer;
}

</style>

</head>

<body>

<div class="quiz-box">

<h2 id="question">Question will appear here</h2>

<button onclick="checkAnswer('A')" id="A"></button>
<button onclick="checkAnswer('B')" id="B"></button>
<button onclick="checkAnswer('C')" id="C"></button>
<button onclick="checkAnswer('D')" id="D"></button>

<p id="score"></p>

</div>

<script>

let questions = [
{
q:"Which drug is used as an osmotic diuretic?",
A:"Furosemide",
B:"Mannitol",
C:"Spironolactone",
D:"Hydrochlorothiazide",
correct:"B"
},

{
q:"Which drug is used in Parkinson's disease?",
A:"Levodopa",
B:"Metformin",
C:"Amoxicillin",
D:"Aspirin",
correct:"A"
},

{
q:"Which drug is an ACE inhibitor?",
A:"Losartan",
B:"Amlodipine",
C:"Enalapril",
D:"Propranolol",
correct:"C"
}

];

let current=0;
let score=0;

function loadQuestion(){

let q=questions[current];

document.getElementById("question").innerText=q.q;
document.getElementById("A").innerText=q.A;
document.getElementById("B").innerText=q.B;
document.getElementById("C").innerText=q.C;
document.getElementById("D").innerText=q.D;

}

function checkAnswer(ans){

if(ans===questions[current].correct){
score++;
}

current++;

if(current<questions.length){
loadQuestion();
}
else{
document.querySelector(".quiz-box").innerHTML=
"<h2>Your Score: "+score+"</h2>";
}

}

loadQuestion();

</script>

</body>
</html>
