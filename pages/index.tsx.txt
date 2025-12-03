// Futuristisches Junior QA Ч Einseitige React-Seite (Deutsch)
// Verwendung:
// - Diese Komponente als Standard-Export in einer Next.js `pages`- oder `app`-Route verwenden oder in Create React App einfugen.
// - Abhangigkeiten: Tailwind CSS + Framer Motion. Optional: lucide-react Icons.
// - Installation: `npm i framer-motion`
// - Tailwind-Konfiguration und globale Styles werden benotigt.

import React, { useState } from 'react';
import { motion } from 'framer-motion';

export default function FuturisticQAde() {
  const [dark, setDark] = useState(true);

  const container = {
    hidden: { opacity: 0, y: 12 },
    show: { opacity: 1, y: 0, transition: { staggerChildren: 0.06 } },
  };

  const item = {
    hidden: { opacity: 0, y: 8 },
    show: { opacity: 1, y: 0 },
  };

  const projects = [
    { title: 'Automatisierte Regression', desc: 'Test-Suite mit Playwright und CI-Integration erstellt', tags: ['Playwright', 'CI'] },
    { title: 'Bug-Triage Dashboard', desc: 'Filterbares Dashboard zur Analyse von flakigen Tests', tags: ['Reporting', 'JS'] },
    { title: 'API-Contract-Tests', desc: 'Vertrags-Tests mit Postman/Newman implementiert', tags: ['API', 'Postman'] },
  ];

  return (
    <div id="top" className={dark ? 'min-h-screen bg-gradient-to-br from-gray-900 via-black to-purple-900 text-slate-100' : 'min-h-screen bg-white text-slate-900'}> 
      <div className="container mx-auto px-6 lg:px-20 py-12">
        {/* Header */}
        <header className="flex items-center justify-between">
          <div className="flex items-center gap-4">
            <div className="w-12 h-12 rounded-xl bg-gradient-to-br from-cyan-400 to-indigo-600 flex items-center justify-center shadow-2xl">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M3 12h18" stroke="white" strokeWidth="1.5" strokeLinecap="round" strokeLinejoin="round" />
                <path d="M12 3v18" stroke="white" strokeWidth="1.5" strokeLinecap="round" strokeLinejoin="round" opacity="0.9" />
              </svg>
            </div>
            <div>
              <h1 className="text-xl font-semibold tracking-tight"><a href="https://example.com" target="_blank" rel="noopener noreferrer">Arsenii Mitchenko</a></h1>
              <p className="text-xs opacity-70">Junior QA Ч Automation | API-Testing | Zuverlassigkeit</p>
            </div>
          </div>

          <div className="flex items-center gap-4">
            <button
              onClick={() => setDark(!dark)}
              className="px-3 py-2 rounded-lg backdrop-blur-md bg-white/5 hover:bg-white/10 border border-white/6"
              aria-label="Thema wechseln"
            >
              {dark ? 'Dunkel' : 'Hell'}
            </button>
            <a href="#contact" className="px-4 py-2 rounded-lg bg-gradient-to-r from-cyan-400 to-indigo-500 text-black font-medium hover:opacity-95">Kontakt</a>
          </div>
        </header>

        {/* Hero */}
        <main className="mt-12 grid lg:grid-cols-3 gap-12 items-start">
          <section className="lg:col-span-2">
            <motion.div initial={{ opacity: 0, x: -20 }} animate={{ opacity: 1, x: 0 }} transition={{ duration: 0.6 }}>
              <h2 className="text-4xl lg:text-5xl font-extrabold leading-tight">Futuristisches QA<br/><span className="text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 to-purple-400">Automation & Zuverlassigkeit</span></h2>
              <p className="mt-4 max-w-xl text-lg opacity-80">Ich entwickle zuverlassige Testautomatisierung, erkenne flakiges Verhalten fruh und verbessere die Produktstabilitat. Schwerpunkt: API-Testing, End-to-End-Automatisierung und CI-Pipelines.</p>

              <div className="mt-6 flex gap-3">
                <a href="https://example.com/Arsenii_Mitchenko_CV.pdf" target="_blank" rel="noopener noreferrer" className="px-4 py-2 rounded-md bg-white/10 border border-white/6">Lebenslauf herunterladen</a> /* «амените ссылку на реальное резюме */
                <a href="#projects" className="px-4 py-2 rounded-md bg-gradient-to-r from-cyan-400 to-indigo-500 text-black">Projekte ansehen</a>
              </div>

              <div className="mt-8 grid grid-cols-2 sm:grid-cols-4 gap-4">
                <Stat label="Automation" value="Playwright, Selenium" />
                <Stat label="API" value="Postman, REST Assured" />
                <Stat label="CI" value="GitHub Actions" />
                <Stat label="Sprachen" value="JS, C# (Lernend)" />
              </div>
            </motion.div>
          </section>

          {/* Side card */}
          <aside>
            <motion.div initial={{ opacity: 0, y: 10 }} animate={{ opacity: 1, y: 0 }} transition={{ delay: 0.2 }} className="p-6 rounded-2xl bg-white/3 border border-white/6 backdrop-blur-md">
              <h3 className="text-sm opacity-80">Kontakt</h3>
              <p className="mt-2 text-sm opacity-70">Berlin Ч Remote moglich</p>

              <div className="mt-4 flex flex-col gap-2 text-xs opacity-85">
                <a href="mailto:mitars.2005@gmail.com" className="hover:underline">mitars.2005@gmail.com</a>
                <a href="https://github.com/yourusername" target="_blank" rel="noopener noreferrer" className="hover:underline">GitHub</a>
                <a href="https://linkedin.com/in/yourprofile" target="_blank" rel="noopener noreferrer" className="hover:underline">LinkedIn</a>
              </div>

              <div className="mt-6">
                <h4 className="text-xs opacity-80">Verfugbarkeit</h4>
                <div className="mt-2 text-sm">Teilzeit / Vollzeit Ч Flexibel</div>
              </div>
            </motion.div>
          </aside>
        </main>

        {/* Projects */}
        <section id="projects" className="mt-16">
          <motion.div variants={container} initial="hidden" animate="show">
            <motion.h3 variants={item} className="text-2xl font-semibold">Ausgewahlte Projekte</motion.h3>
            <motion.div variants={item} className="mt-6 grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
              {projects.map((p, i) => (
                <motion.article key={i} className="p-6 rounded-2xl bg-white/4 border border-white/6 backdrop-blur-md hover:scale-[1.02] transition-transform" whileHover={{ y: -6 }}>
                  <h4 className="font-semibold">{p.title}</h4>
                  <p className="mt-2 text-sm opacity-80">{p.desc}</p>
                  <div className="mt-4 flex flex-wrap gap-2">
                    {p.tags.map((t) => <span key={t} className="text-xs px-2 py-1 rounded bg-white/6">{t}</span>)}
                  </div>
                </motion.article>
              ))}
            </motion.div>
          </motion.div>
        </section>

        {/* Skills & Tools */}
        <section className="mt-12 grid md:grid-cols-3 gap-6">
          <div className="md:col-span-2 p-6 rounded-2xl bg-white/3 border border-white/6">
            <h4 className="font-semibold">Fahigkeiten</h4>
            <ul className="mt-4 grid grid-cols-2 gap-2 text-sm opacity-85">
              <li>End-to-End-Automatisierung (Playwright)</li>
              <li>API-Testing (Postman/Newman)</li>
              <li>CI/CD-Pipelines (GitHub Actions)</li>
              <li>Bug-Triage und Reporting</li>
              <li>Grundlegendes Scripting (JS, Grundlagen C#)</li>
              <li>Test-Design & Umgang mit flakigen Tests</li>
            </ul>
          </div>

          <div className="p-6 rounded-2xl bg-white/3 border border-white/6">
            <h4 className="font-semibold">Tools</h4>
            <div className="mt-4 flex flex-wrap gap-2 text-sm opacity-85">
              {['Playwright','Postman','Jira','GitHub','Docker','VSCode'].map(t => <span key={t} className="px-2 py-1 rounded bg-white/6">{t}</span>)}
            </div>
          </div>
        </section>

        {/* Contact Form */}
        <section id="contact" className="mt-12 p-6 rounded-2xl bg-gradient-to-br from-black/20 to-white/3 border border-white/5 backdrop-blur-md">
          <h3 className="text-xl font-semibold">Kontakt aufnehmen</h3>
          <p className="mt-2 text-sm opacity-80">Lieber per E?Mail? Nutze das Formular oder klicke den Mail-Link.</p>

          <form onSubmit={(e) => {
            e.preventDefault();
            const form = e.target;
            const data = new FormData(form);
            const payload = Object.fromEntries(data.entries());

            // Einfacher client-seitiger Fallback: offne mailto mit ausgefulltem Inhalt
            const subject = encodeURIComponent(`Kontakt uber Webseite: ${payload.subject || 'Hallo'}`);
            const body = encodeURIComponent(`Name: ${payload.name}%0AEmail: ${payload.email}%0ANachricht:%0A${payload.message}`);
            window.location.href = `mailto:mitars.2005@gmail.com?subject=${subject}&body=${body}`;
          }} className="mt-4 grid grid-cols-1 md:grid-cols-2 gap-4">
            <input name="name" placeholder="Dein Name" required className="p-3 rounded-md bg-white/4 border border-white/6" />
            <input name="email" placeholder="Deine E?Mail" required className="p-3 rounded-md bg-white/4 border border-white/6" />
            <input name="subject" placeholder="Betreff" className="p-3 rounded-md bg-white/4 border border-white/6 md:col-span-2" />
            <textarea name="message" placeholder="Nachricht" rows={6} className="p-3 rounded-md bg-white/4 border border-white/6 md:col-span-2" />

            <div className="md:col-span-2 flex items-center justify-between">
              <div className="text-xs opacity-80">Oder direkt per E?Mail: <a href="mailto:mitars.2005@gmail.com" className="underline">mitars.2005@gmail.com</a></div>
              <button type="submit" className="px-4 py-2 rounded-md bg-gradient-to-r from-cyan-400 to-indigo-500 text-black">Senden</button>
            </div>
          </form>
        </section>

        {/* Footer */}
        <footer className="mt-12 text-center text-xs opacity-70">© {new Date().getFullYear()} Arsenii Ч Junior QA. Made with ?</footer>

      </div>
    </div>
  );
}

function Stat({ label, value }){
  return (
    <div className="p-3 rounded-lg bg-white/3 border border-white/6">
      <div className="text-xs opacity-80">{label}</div>
      <div className="mt-1 font-medium text-sm">{value}</div>
    </div>
  );
}
