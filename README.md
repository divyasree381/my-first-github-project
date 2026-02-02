 <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Divya Sree | Full Stack Developer</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
    scroll-behavior:smooth;
}

body{
    background:linear-gradient(135deg,#0f172a,#1e293b);
    color:white;
}

nav{
    position:fixed;
    width:100%;
    top:0;
    display:flex;
    justify-content:space-between;
    padding:20px 10%;
    background:rgba(15,23,42,0.8);
    backdrop-filter:blur(10px);
    z-index:1000;
}

nav a{
    color:white;
    text-decoration:none;
    margin-left:20px;
    font-weight:500;
}

nav a:hover{
    color:#38bdf8;
}

section{
    padding:100px 10%;
}

.hero{
    height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
}

.hero h1{
    font-size:3rem;
}

.hero span{
    color:#38bdf8;
}

.typing{
    font-size:1.3rem;
    margin-top:10px;
    color:#94a3b8;
}

.btn{
    margin-top:25px;
    padding:12px 28px;
    background:#38bdf8;
    color:#0f172a;
    border:none;
    border-radius:30px;
    cursor:pointer;
    font-weight:600;
    text-decoration:none;
    display:inline-block;
    transition:0.3s;
}

.btn:hover{
    transform:scale(1.05);
    background:#0ea5e9;
}

.section-title{
    font-size:2rem;
    margin-bottom:40px;
    color:#38bdf8;
}

.card-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:25px;
}

.card{
    background:rgba(255,255,255,0.05);
    padding:25px;
    border-radius:15px;
    transition:0.4s;
    backdrop-filter:blur(10px);
}

.card:hover{
    transform:translateY(-10px);
    box-shadow:0 10px 30px rgba(56,189,248,0.3);
}

footer{
    text-align:center;
    padding:30px;
    background:#0f172a;
    color:#94a3b8;
}

.fade{
    opacity:0;
    transform:translateY(30px);
    transition:all 1s ease;
}

.fade.show{
    opacity:1;
    transform:translateY(0);
}
</style>
</head>

<body>

<nav>
    <h3>Divya Sree</h3>
    <div>
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
    </div>
</nav>

<section class="hero">
    <h1>Hi, I'm <span>Divya Sree</span></h1>
    <div class="typing" id="typing"></div>
    <a href="#projects" class="btn">View My Work</a>
</section>

<section id="about" class="fade">
    <h2 class="section-title">About Me</h2>
    <p>
    I am a B.Tech Computer Science student at 
    <strong>Avanthi Institute of Engineering and Technology</strong>.
    I specialize in Full Stack Development and have strong foundations in 
    HTML, CSS, SQL and modern web technologies.
    I am actively seeking offline and online internship opportunities 
    where I can contribute, learn and grow as a developer.
    </p>
</section>

<section id="skills" class="fade">
    <h2 class="section-title">Skills</h2>
    <div class="card-grid">
        <div class="card">
            <h3>Frontend</h3>
            <p>HTML, CSS, Responsive Design</p>
        </div>
        <div class="card">
            <h3>Backend</h3>
            <p>Full Stack Development, REST APIs</p>
        </div>
        <div class="card">
            <h3>Database</h3>
            <p>SQL, Database Design</p>
        </div>
        <div class="card">
            <h3>Tools</h3>
            <p>Git, GitHub, VS Code</p>
        </div>
    </div>
</section>

<section id="projects" class="fade">
    <h2 class="section-title">Projects</h2>
    <div class="card-grid">
        <div class="card">
            <h3>AI Chatbot Web Application</h3>
            <p>
            Developed a full-stack chatbot system with authentication 
            and chat history management.
            </p>
        </div>
        <div class="card">
            <h3>Brain Tumor Detection</h3>
            <p>
            Machine learning model to detect tumors from MRI scans.
            </p>
        </div>
    </div>
</section>

<section id="contact" class="fade">
    <h2 class="section-title">Contact</h2>
    <p>Email: your-email@example.com</p>
    <p>LinkedIn: linkedin.com/in/yourprofile</p>
    <p>GitHub: github.com/yourusername</p>
    <br>
    <a href="#" class="btn">Download Resume</a>
</section>

<footer>
    © 2026 Divya Sree | Full Stack Developer
</footer>

<script>
// Typing animation
const text = ["Full Stack Developer",
              "Open to Internships",
              "Passionate Problem Solver"];
let i=0, j=0, current="", isDeleting=false;
function type(){
    if(i<text.length){
        if(!isDeleting && j<=text[i].length){
            current=text[i].substring(0,j++);
        }else if(isDeleting && j>=0){
            current=text[i].substring(0,j--);
        }
        document.getElementById("typing").textContent=current;
        if(j==text[i].length) isDeleting=true;
        if(j==0 && isDeleting){
            isDeleting=false;
            i++;
        }
    }else{
        i=0;
    }
    setTimeout(type,100);
}
type();

// Fade-in animation
const faders=document.querySelectorAll('.fade');
const appearOptions={threshold:0.3};
const appearOnScroll=new IntersectionObserver(function(entries){
    entries.forEach(entry=>{
        if(entry.isIntersecting){
            entry.target.classList.add("show");
        }
    });
},appearOptions);
faders.forEach(fader=>{
    appearOnScroll.observe(fader);
});
</script>

</body>
</html>
