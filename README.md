# Hi there, I'm Diogo Santos! 👋

## 🎓 About Me
I am a **Computer Graphics Engineer** currently enrolled in a **Informatics Engineering Master's studen**at **IPVC (Instituto Politécnico de Viana do Castelo)**, currently finishing my thesis/final year. My focus is on building scalable, high-performance web applications.

* Currently working with **React, Node.js, and Express**.
* Finishing my Master's in **Informatics Engineering**.
* Interested in Web Architecture, Cloud Computing, and Clean Code.
* Reach me at: **sdsantosdiogo@gmail.com**

---
## 🛠 Tech Stack

"use client";
import { useState } from "react";
import { motion, AnimatePresence } from "framer-motion";
import Link from "next/link";
import { 
  Github, Linkedin, Mail, Cpu, Cloud,
  Terminal, ChevronDown, FolderCode, MapPin, Database, Binary
} from "lucide-react";

type Language = 'pt' | 'en';

const translations = {
  pt: {
    role: "Computer Graphics Engineer",
    aboutTitle: "01. Percurso",
    aboutText: "Mestrando em Engenharia Informática no IPVC. Especialista na convergência entre infraestrutura backend escalável e computação visual de alta performance.",
    techStack: "02. Ecossistema Técnico",
    theory: "Engenharia de software aplicada à computação gráfica.",
    viewGithub: "GitHub",
    viewProjects: "Explorar Projetos",
    location: "Viana do Castelo, Portugal"
  },
  en: {
    role: "Computer Graphics Engineer",
    aboutTitle: "01. Path",
    aboutText: "Informatics Engineering Master's student at IPVC. Specialist in the convergence between scalable backend infrastructure and high-performance visual computing.",
    techStack: "02. Technical Ecosystem",
    theory: "Software engineering applied to computer graphics.",
    viewGithub: "GitHub",
    viewProjects: "Explore Projects",
    location: "Viana do Castelo, Portugal"
  }
};

const techStack = {
  web: {
    title: "Web & Backend",
    icon: <Terminal size={16} />,
    skills: [
      { name: "HTML5", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" },
      { name: "CSS3", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" },
      { name: "React", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" },
      { name: "Node.js", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" },
      { name: "Java", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" },
      { name: "C#", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg" },
      { name: ".NET", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dotnetcore/dotnetcore-original.svg" }
    ]
  },
  cloud: {
    title: "Cloud Services",
    icon: <Cloud size={16} />,
    skills: [
      { name: "Azure", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg" },
      { name: "AWS", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-plain-wordmark.svg" },
      { name: "GCP", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/googlecloud/googlecloud-original.svg" }
    ]
  },
  data: {
    title: "Data & Tools",
    icon: <Database size={16} />,
    skills: [
      { name: "SQL Server", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/microsoftsqlserver/microsoftsqlserver-plain.svg" },
      { name: "Redis", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redis/redis-original.svg" },
      { name: "Docker", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" },
      { name: "GitHub", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" }
    ]
  },
  graphics: {
    title: "Graphics & 3D",
    icon: <Binary size={16} />,
    skills: [
      { name: "Unity", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/unity/unity-original.svg" },
      { name: "Blender", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/blender/blender-original.svg" },
      { name: "Maya", url: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/maya/maya-original.svg" }
    ]
  }
};

export default function PersonalPortfolio() {
  const [lang, setLang] = useState<Language>("en");
  const [isLangOpen, setIsLangOpen] = useState(false);
  const t = translations[lang];

  const btnBase = "flex items-center gap-3 px-6 py-3 rounded-xl transition-all font-semibold text-base border";
  const primaryBtn = `${btnBase} bg-white text-black hover:bg-blue-400 border-transparent shadow-lg shadow-blue-500/10`;
  const secondaryBtn = `${btnBase} bg-[#161b22] border-[#30363d] text-[#c9d1d9] hover:border-[#8b949e] hover:bg-[#21262d]`;

  return (
    <main className="min-h-screen bg-[#0d1117] text-[#c9d1d9] font-sans selection:bg-blue-500/30 overflow-x-hidden">
      
      {/* Lang Selector */}
      <nav className="fixed top-8 right-8 z-50" onMouseLeave={() => setIsLangOpen(false)}>
        <button 
          onClick={() => setIsLangOpen(!isLangOpen)}
          className="bg-[#161b22] border border-[#30363d] px-4 py-2 rounded-lg text-sm font-mono hover:text-white transition-all flex items-center gap-2"
        >
          {lang.toUpperCase()} <ChevronDown size={14} />
        </button>
        <AnimatePresence>
          {isLangOpen && (
            <motion.div initial={{ opacity: 0, y: -10 }} animate={{ opacity: 1, y: 0 }} className="absolute right-0 mt-2 bg-[#161b22] border border-[#30363d] rounded-lg overflow-hidden shadow-2xl">
              {['pt', 'en'].map((l) => (
                <button key={l} onClick={() => { setLang(l as Language); setIsLangOpen(false); }} className="block w-full px-6 py-3 text-left hover:bg-blue-600 hover:text-white text-sm font-mono capitalize">
                  {l === 'pt' ? 'Português' : 'English'}
                </button>
              ))}
            </motion.div>
          )}
        </AnimatePresence>
      </nav>

      <div className="max-w-5xl mx-auto px-8 pt-40 pb-32">
        <header className="mb-32">
          <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }}>
            <div className="flex items-center gap-3 text-blue-400 font-mono text-sm mb-4 uppercase tracking-[0.3em]">
              <MapPin size={16} /> {t.location}
            </div>
            <h1 className="text-6xl md:text-8xl font-bold text-white mb-6 tracking-tighter">
              Diogo Santos<span className="text-blue-500">.</span>
            </h1>
            <p className="text-2xl md:text-4xl text-[#8b949e] mb-12 font-light leading-tight max-w-3xl">
              {t.role} <span className="text-[#30363d]">/</span> MSc Student
            </p>
            
            <div className="flex flex-wrap gap-4">
              <Link href="/projetos" className={primaryBtn}>
                <FolderCode size={20} /> {t.viewProjects}
              </Link>
              <a href="https://github.com/diogosantos25426" target="_blank" className={secondaryBtn}>
                <Github size={20} /> {t.viewGithub}
              </a>
              <a href="mailto:sdsantosdiogo@gmail.com" className={secondaryBtn}>
                <Mail size={20} /> Email
              </a>
            </div>
          </motion.div>
        </header>

        <section className="grid gap-32">
          {/* Bio Section */}
          <div className="grid md:grid-cols-12 gap-8">
            <h2 className="md:col-span-4 text-white text-xs uppercase tracking-[0.2em] font-bold opacity-30">
              {t.aboutTitle}
            </h2>
            <div className="md:col-span-8 italic font-light">
              <p className="text-2xl md:text-3xl text-[#e6edf3] leading-relaxed">
                "{t.aboutText}"
              </p>
            </div>
          </div>

          {/* New Tech Stack Grid */}
          <div className="grid md:grid-cols-12 gap-8">
            <h2 className="md:col-span-4 text-white text-xs uppercase tracking-[0.2em] font-bold opacity-30 mt-2">
              {t.techStack}
            </h2>
            <div className="md:col-span-8 grid grid-cols-1 sm:grid-cols-2 gap-16">
              {Object.entries(techStack).map(([key, group]) => (
                <div key={key} className="space-y-8">
                  <h3 className="flex items-center gap-3 text-white font-mono text-sm uppercase tracking-widest opacity-80 border-b border-[#30363d] pb-4">
                    {group.icon} {group.title}
                  </h3>
                  <div className="grid grid-cols-2 gap-y-6">
                    {group.skills.map((skill) => (
                      <div key={skill.name} className="flex items-center gap-3 group cursor-default">
                        <img 
                          src={skill.url} 
                          alt={skill.name} 
                          className="w-8 h-8 grayscale group-hover:grayscale-0 transition-all duration-300 transform group-hover:scale-110" 
                        />
                        <span className="text-[#8b949e] group-hover:text-white transition-colors font-medium">
                          {skill.name}
                        </span>
                      </div>
                    ))}
                  </div>
                </div>
              ))}
            </div>
          </div>

          {/* GitHub Streak - Larga */}
          <div className="p-8 bg-[#161b22] border border-[#30363d] rounded-2xl flex flex-col md:flex-row items-center justify-between gap-10">
            <div className="space-y-2">
              <div className="flex items-center gap-2 text-blue-400 font-mono text-xs uppercase tracking-widest">
                <Cpu size={14} /> Dev Activity
              </div>
              <h3 className="text-2xl font-semibold text-white font-mono tracking-tighter">System.Engagement</h3>
              <p className="text-[#8b949e] italic font-light">{t.theory}</p>
            </div>
            <img 
              src="https://github-readme-streak-stats.herokuapp.com/?user=diogosantos25426&theme=dark&hide_border=true&background=161b22&ring=3b82f6&stroke=3b82f6" 
              alt="Streak"
              className="w-full md:w-auto h-24 object-contain opacity-90"
            />
          </div>
        </section>

        <footer className="mt-40 pt-12 border-t border-[#30363d] flex flex-col md:flex-row justify-between items-center gap-6 text-[#8b949e] font-mono text-[10px] uppercase tracking-[0.3em]">
          <p>© {new Date().getFullYear()} Diogo Santos — MSc Engineer</p>
          <div className="flex gap-8">
             <a href="https://linkedin.com" className="hover:text-blue-400 transition-colors">LinkedIn</a>
             <a href="https://github.com/diogosantos25426" className="hover:text-blue-400 transition-colors">GitHub</a>
          </div>
        </footer>
      </div>
    </main>
  );
}
---

## 📈 GitHub Activities
<p align="center">
<img src="https://github-readme-streak-stats.herokuapp.com/?user=diogosantos25426&theme=vibrant&hide_border=true" alt="streak stats" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Main_Stack-React_%7C_Node-blue?style=flat-square">
  <img src="https://img.shields.io/badge/Specialization-Graphics_Engineering-orange?style=flat-square">
</p>

---

## 🔗 Let's Connect
<p align="left">
  <a href="[https://www.linkedin.com/in/diogo-santos-77b214353/]" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
</p>

---
<p align="center">
  "Turning coffee into code and academic theory into real-world solutions."
</p>
