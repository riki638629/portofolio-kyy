# portofolio-kyy<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>kyy | Gen Z Aesthetic Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://unpkg.com/aos@2.3.1/dist/aos.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/vanilla-tilt/1.7.0/vanilla-tilt.min.js"></script>

    <style>
        /* PENTING: VAR & RESET (MINIMAL) */
        :root{--c-bg:#0a0a1a;--c-p:#ff00ff;--c-s:#00ffff;--c-t:#f0f0f0;--c-a:#ffeb3b;--s-p:0 0 10px var(--c-p);--s-s:0 0 10px var(--c-s);}
        *{margin:0;padding:0;box-sizing:border-box;}
        body{
            font-family:'Poppins',sans-serif;
            background-color:var(--c-bg); 
            color:var(--c-t);line-height:1.6;min-height:100vh;
            background-attachment:fixed;overflow-x:hidden;
            position: relative;
        }
        
        /* 🎥 VIDEO BACKGROUND STYLES */
        #video-background {
            position: fixed;
            right: 0;
            bottom: 0;
            min-width: 100%;
            min-height: 100%;
            width: auto;
            height: auto;
            z-index: -100;
            overflow: hidden;
            filter: brightness(60%) contrast(120%); 
        }

        /* Pastikan konten utama selalu di atas video */
        main {
            position: relative;
            z-index: 1; 
        }
        
        /* UTILITAS (GLASSMORPHISM) */
        .glass{background:rgba(255,255,255,.05);backdrop-filter:blur(15px);border-radius:15px;border:1px solid rgba(255,255,255,.1);box-shadow:0 4px 30px rgba(0,0,0,.1);transition:all .3s ease;}

        /* LAYOUT & TYPOGRAPHY */
        .pad{padding:100px 5% 50px;max-width:1200px;margin:0 auto;}
        .title{font-size:3em;text-align:center;margin-bottom:60px;font-weight:900;text-transform:uppercase;color:var(--c-s);text-shadow:var(--s-s);}

        /* NAVBAR */
        .nav{display:flex;justify-content:space-between;align-items:center;padding:20px 5%;position:sticky;top:0;z-index:1000;background:rgba(10,10,26,.9);backdrop-filter:blur(8px);border-bottom:1px solid rgba(255,255,255,.05);}
        .logo{font-size:1.8em;font-weight:900;color:var(--c-a);text-shadow:0 0 5px var(--c-a);}
        .nav ul{list-style:none;display:flex;}
        .nav ul li{margin:0 15px;}
        .neon-link{text-decoration:none;color:var(--c-t);font-weight:600;transition:all .3s;}
        .neon-link:hover{color:var(--c-s);text-shadow:var(--s-s);}
        .ham{display:none;font-size:2em;cursor:pointer;color:var(--c-s);}
        
        /* BUTTONS */
        .btn-p,.btn-s{padding:10px 20px;border:none;border-radius:50px;font-weight:700;cursor:pointer;margin-left:10px;text-transform:uppercase;transition:all .3s;}
        .btn-p{background-color:var(--c-p);color:var(--c-bg);box-shadow:0 0 10px var(--c-p);}
        .btn-p:hover{box-shadow:0 0 15px var(--c-p),0 0 30px var(--c-p);transform:translateY(-2px);}
        .btn-s{background:none;border:2px solid var(--c-s);color:var(--c-s);box-shadow:0 0 5px var(--c-s);}
        .btn-s:hover{background-color:var(--c-s);color:var(--c-bg);box-shadow:0 0 15px var(--c-s),0 0 30px var(--c-s);transform:translateY(-2px);}

        /* HERO SECTION */
        .hero{display:flex;align-items:center;justify-content:space-between;padding:150px 5%;min-height:90vh;max-width:1200px;margin:0 auto;}
        .hero h1{font-size:4.5em;margin-bottom:20px;font-weight:900;line-height:1.1;color:var(--c-p);}
        
        /* GLITCH & TYPING (KRITIS) */
        .glitch{position:relative;animation:glitch-anim 2s infinite linear alternate-reverse;}
        .glitch::before,.glitch::after{content:attr(data-text);position:absolute;top:0;left:0;width:100%;height:100%;}
        .glitch::before{left:2px;text-shadow:-2px 0 var(--c-s);clip:rect(44px,450px,56px,0);animation:glitch-anim-before 3s infinite linear alternate-reverse;}
        .glitch::after{left:-2px;text-shadow:-2px 0 var(--c-a);clip:rect(85px,450px,100px,0);animation:glitch-anim-after 5s infinite linear alternate-reverse;}
        @keyframes glitch-anim{0%,100%{transform:translate(0);}20%{transform:translate(-2px,2px);}40%{transform:translate(-2px,-2px);}60%{transform:translate(2px,2px);}80%{transform:translate(2px,-2px);}}
        @keyframes glitch-anim-before{0%{clip:rect(44px,450px,56px,0);}15%{clip:rect(65px,450px,75px,0);}30%{clip:rect(25px,450px,40px,0);}45%{clip:rect(80px,450px,90px,0);}100%{clip:rect(44px,450px,56px,0);}}
        @keyframes glitch-anim-after{0%{clip:rect(85px,450px,100px,0);}15%{clip:rect(10px,450px,20px,0);}30%{clip:rect(50px,450px,65px,0);}45%{clip:rect(30px,450px,40px,0);}100%{clip:rect(85px,450px,100px,0);}}
        .typing::after{content:'|';display:inline-block;animation:cursor-blink .7s infinite;color:var(--c-s);text-shadow:0 0 5px var(--c-s);}
        @keyframes cursor-blink{0%,100%{opacity:1;}50%{opacity:0;}}

        /* HERO ORB & FOTO */
        .hero-img{
            width:300px;
            height:300px;
            background:linear-gradient(45deg,var(--c-p),var(--c-s));
            border-radius:50%;
            position:relative;
            animation:floating 6s infinite ease-in-out;
            box-shadow:0 0 40px rgba(255,0,255,.5),0 0 80px rgba(0,255,255,.5);
            overflow: hidden; 
        }

        .profile-photo {
            width: 100%;
            height: 100%;
            object-fit: cover; 
            border-radius: 50%;
            display: block;
        }

        @keyframes floating{0%{transform:translate(0,0)scale(1);}50%{transform:translate(10px,-15px)scale(1.05);}100%{transform:translate(0,0)scale(1);}}
        .social a{color:var(--c-p);text-decoration:none;transition:all .3s;padding:5px 10px;}
        .social a:hover{color:var(--c-a);text-shadow:0 0 10px var(--c-a);}
        
        /* SKILLS & PROJECTS */
        .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:20px;}
        .card{padding:25px;text-align:center;position:relative;cursor:pointer;}
        .card:hover{box-shadow:0 0 30px rgba(0,0,0,.3),var(--s-s);border-color:var(--c-s);transform:scale(1.02);}
        .p-card:hover{box-shadow:0 0 30px rgba(0,0,0,.3),var(--s-p);border-color:var(--c-p);transform:translateY(-5px);}
        .skill-icon{font-size:3em;color:var(--c-a);margin-bottom:10px;text-shadow:0 0 10px var(--c-a);}
        .p-card h3{color:var(--c-p);font-weight:700;margin-bottom:10px;text-shadow:0 0 5px var(--c-p);}

        /* MODAL (Ditambahkan Image Tag untuk Preview) */
        .modal{display:none;position:fixed;z-index:2000;left:0;top:0;width:100%;height:100%;overflow:auto;background-color:rgba(0,0,0,.8);backdrop-filter:blur(5px);padding-top:50px;}
        .modal-content{margin:5% auto;padding:40px;width:80%;max-width:700px;position:relative;animation:slideIn .4s;}
        .close{color:var(--c-s);float:right;font-size:28px;font-weight:bold;cursor:pointer;text-shadow:var(--s-s);}
        .close:hover{color:var(--c-p);text-shadow:var(--s-p);}
        @keyframes slideIn{from{transform:translateY(-50px);opacity:0;}to{transform:translateY(0);opacity:1;}}

        /* RESPONSIVE MOBILE */
        @media(max-width:900px){
            .hero{flex-direction:column;text-align:center;padding:100px 5%;min-height:auto;}
            .hero h1{font-size:3em;}
            .typing{font-size:1.2em;}
            .hero-img{width:200px;height:200px;}
            .nav ul{display:none;flex-direction:column;width:100%;position:absolute;top:80px;left:0;background:rgba(10,10,26,.95);backdrop-filter:blur(10px);padding:20px 0;}
            .nav ul.open{display:flex;}
            .nav ul li{margin:10px 0;text-align:center;}
            .ham{display:block;}
            .cta-buttons{display:none;}
        }
    </style>
</head>
<body>

    <video autoplay loop muted playsinline id="video-background">
        <source src="kyy.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

    <main id="main-content">
        <nav class="nav">
            <div class="logo">⚡ KYY•DEV</div>
            <ul id="nav-links">
                <li><a href="#hero" class="neon-link">Home</a></li>
                <li><a href="#skills" class="neon-link">Skills</a></li>
                <li><a href="#projects" class="neon-link">Projects</a></li>
                <li class="mobile-cta-item"><a href="riki567392@gmail.com" class="btn-p">HIRE ME</a></li>
                <li class="mobile-cta-item"><a href="#" class="btn-s">Download CV</a></li>
            </ul>
            <div class="cta-buttons desktop-only">
                <a href="mailto:hello@example.com" class="btn-p">HIRE ME</a>
                <a href="#" class="btn-s">Download CV</a>
            </div>
            <div class="ham" id="hamburger">&#9776;</div>
        </nav>

        <section id="hero" class="hero">
            <div class="hero-content" data-aos="fade-right" data-aos-delay="200">
                <h1 class="glitch" data-text="HEY, I'M GEN-Z DEVS">HEY, I'M GEN-Z DEVS</h1>
                <p class="typing" style="font-size:1.5em;font-weight:300;min-height:1.5em;"></p>
                <p style="margin-top:15px;font-weight:300;">Tech Enthusiast, Aesthetic Builder, and Digital Creator.</p>
                <div class="social" style="margin-top:20px;">
                    <a href="#">Instagram</a><a href="#">GitHub</a><a href="#">Telegram</a>
                </div>
            </div>
            
            <div class="hero-img" data-aos="zoom-in" data-aos-delay="400">
                <img src="kyy.jpg" alt="Your Profile Picture" class="profile-photo">
            </div>
        </section>

        <section id="skills" class="pad">
            <h2 class="title" data-aos="fade-up">🔧 Tech & Vibe Skillset</h2>
            <div class="grid" id="skills-grid"></div>
        </section>

        <section id="projects" class="pad">
            <h2 class="title" data-aos="fade-up">🤓kyy Projects</h2>
            <div class="grid" id="projects-grid" style="grid-template-columns:repeat(auto-fit,minmax(300px,1fr));"></div>
        </section>

        <footer class="pad" style="text-align:center;padding:30px 5%;">
            <p>&copy; 2025 kyy GENZ Portfolio</p>
        </footer>
    </main>

    <div id="project-modal" class="modal">
        <div class="modal-content glass">
            <span class="close">&times;</span>
            <h3 id="modal-title" class="title" style="font-size:1.8em;margin-bottom:20px;"></h3>
            
            <img id="modal-image" src="" alt="Project Image Preview" style="width:100%;height:auto;border-radius:10px;margin-bottom:20px;display:none;">

            <p id="modal-description"></p>
            <p id="modal-tech" style="margin-top:15px;font-style:italic;color:var(--c-a);"></p>
            <div class="modal-actions" style="margin-top:30px;display:flex;gap:15px;">
                <a id="modal-live-link" href="#" target="_blank" class="btn-p" style="display:none;">Live Preview</a>
                <a id="modal-github-link" href="#" target="_blank" class="btn-s" style="display:none;">GitHub Repo</a>
            </div>
        </div>
    </div>


    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        // ===========================================
        // 💾 DATA SKILLS & PROJECTS
        // ===========================================
        const SKILLS = [
            {name:"HTML",icon:"📑"},
            {name:"CSS",icon:"🎨"},
            {name:"JavaScript",icon:"💻"},
            {name:"Python",icon:"🐍"},
            {name:"Tailwind CSS",icon:"💎"},
        ];

        const PROJECTS = [
            {
                title:"Website Sosial Boost",
                desc:"Platform boost sosial media dengan auto design dan UI aesthetic. Lengkapi deskripsi ini dengan detail proyek Anda.",
                tech:"HTML, CSS, JS",
                live:"#", 
                github:"#", 
                image:"path/to/project-sosialboost.jpg" 
            },
            {
                title:"AI Photo Enhancer",
                desc:"Aplikasi ubah foto low-res jadi HD (Mirip Remini). Jelaskan teknologi dan fitur utama.",
                tech:"Backend Python, Frontend HTML/CSS/JS",
                live:"#", 
                github:"#", 
                image:"path/to/project-ai-enhancer.jpg"
            },
            {
                title:"Portfolio Animasi Aesthetic",
                desc:"Eksperimen portofolio GSAP + Tilt effect, hero section neon floating. Ini adalah proyek yang sedang Anda kerjakan!",
                tech:"GSAP, Tilt effect",
                live:"#", 
                github:"#", 
                image:"path/to/project-portfolio.jpg"
            },
            // Tambahkan proyek lain jika ada
        ];
        // ===========================================


        document.addEventListener('DOMContentLoaded', () => {
            // GENERATE CONTENT
            const skillGrid = document.getElementById('skills-grid'), projGrid = document.getElementById('projects-grid');
            SKILLS.forEach((s, i) => {
                skillGrid.innerHTML += `<div class="card glass" data-aos="fade-up" data-aos-delay="${i*80}"><div class="skill-icon">${s.icon}</div><h4>${s.name}</h4></div>`;
            });
            PROJECTS.forEach((p, i) => {
                const card = document.createElement('div');
                card.className = 'p-card glass card';
                card.setAttribute('data-aos', 'zoom-in-up');
                card.setAttribute('data-aos-delay', i * 100);
                card.onclick = () => openModal(p);
                card.innerHTML = `<h3>${p.title}</h3><p>${p.desc}</p><p style="font-size:.9em;color:var(--c-s);margin-top:10px;">Tech: ${p.tech}</p>`;
                projGrid.appendChild(card);
            });

            // INIT ANIMATION
            AOS.init({duration:800,once:true,});
            VanillaTilt.init(document.querySelectorAll(".card"),{max:10,speed:400,glare:true,"max-glare":0.2,});

            // TYPING EFFECT
            const tEl = document.querySelector('.typing');
            const tArr = ["Designer.", "Developer.", "PROGAMER.", "Innovator."];
            let tI=0,cI=0;
            const type = () => {
                if(cI < tArr[tI].length){tEl.textContent += tArr[tI].charAt(cI++);setTimeout(type,80);}else{setTimeout(erase,1500);}
            }
            const erase = () => {
                if(cI > 0){tEl.textContent = tArr[tI].substring(0,--cI);setTimeout(erase,50);}else{tI=(tI+1)%tArr.length;setTimeout(type,500);}
            }
            type();

            // 💡 FUNGSI MODAL BARU (Mendukung Gambar & Link)
            const modal = document.getElementById("project-modal"), closeBtn = document.querySelector(".close");
            const mTitle = document.getElementById("modal-title"), mDesc = document.getElementById("modal-description");
            const mTech = document.getElementById("modal-tech"), mLive = document.getElementById("modal-live-link"), mGit = document.getElementById("modal-github-link");
            const mImage = document.getElementById("modal-image"); 

            const openModal = (p) => {
                mTitle.textContent = p.title; 
                mDesc.textContent = p.desc; 
                mTech.textContent = `Teknologi: ${p.tech}`;
                
                // 1. Atur Gambar Modal
                if (p.image && p.image !== '#') {
                    mImage.src = p.image;
                    mImage.style.display = 'block'; 
                } else {
                    mImage.style.display = 'none'; 
                }

                // 2. Atur Link dan Tampilkan Tombol
                mLive.href = p.live; // Mengambil link dari data
                mGit.href = p.github; // Mengambil link dari data
                
                // Tampilkan tombol hanya jika linknya ada dan bukan '#'
                mLive.style.display = p.live && p.live !== '#' ? 'inline-block' : 'none'; 
                mGit.style.display = p.github && p.github !== '#' ? 'inline-block' : 'none';
                
                modal.style.display = "block";
            }

            closeBtn.onclick = () => modal.style.display = "none";
            window.onclick = (e) => {if (e.target == modal) {modal.style.display = "none";}}

            // HAMBURGER
            const ham = document.getElementById('hamburger'), nav = document.getElementById('nav-links');
            ham.addEventListener('click', () => nav.classList.toggle('open'));
            document.querySelectorAll('#nav-links a').forEach(link => {
                link.addEventListener('click', () => nav.classList.remove('open'));
            });
        });
    </script>
</body>
</html>![d0b528ad40ed73851e05cf8b1addc72e](https://github.com/user-attachments/assets/4f1a5068-9b59-45f2-a7d0-b2edea5429a6)
