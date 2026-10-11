from pathlib import Path

path = Path("/mnt/data/README_Santhosh_Final.md")
readme = path.read_text(encoding="utf-8")

# Replace tech stack section with 3-column, centered tables.
start = readme.index("## 🧰 TECH STACK")
end = readme.index("\n---\n\n## 🚀 PROJECTS", start)

tech = r'''## 🧰 TECH STACK

<div align="center">

<table>
<tr><th colspan="3" align="center">⌨️ PROGRAMMING LANGUAGES</th></tr>
<tr>
<td align="center" width="33%"><img src="https://skillicons.dev/icons?i=java" width="48" alt="Java"/><br/><b>Java</b></td>
<td align="center" width="33%"><img src="https://skillicons.dev/icons?i=python" width="48" alt="Python"/><br/><b>Python</b></td>
<td align="center" width="33%"><img src="https://skillicons.dev/icons?i=javascript" width="48" alt="JavaScript"/><br/><b>JavaScript</b></td>
</tr>
<tr><th colspan="3" align="center">🎨 FRONTEND DEVELOPMENT</th></tr>
<tr>
<td align="center"><img src="https://skillicons.dev/icons?i=html" width="48" alt="HTML5"/><br/><b>HTML5</b></td>
<td align="center"><img src="https://skillicons.dev/icons?i=css" width="48" alt="CSS3"/><br/><b>CSS3</b></td>
<td align="center"><img src="https://skillicons.dev/icons?i=react" width="48" alt="React"/><br/><b>React</b></td>
</tr>
<tr><td colspan="3" align="center"><img src="https://skillicons.dev/icons?i=bootstrap" width="48" alt="Bootstrap"/><br/><b>Bootstrap</b></td></tr>
<tr><th colspan="3" align="center">⚙️ BACKEND DEVELOPMENT</th></tr>
<tr>
<td align="center"><img src="https://skillicons.dev/icons?i=nodejs" width="48" alt="Node.js"/><br/><b>Node.js</b></td>
<td align="center"><img src="https://skillicons.dev/icons?i=express" width="48" alt="Express.js"/><br/><b>Express.js</b></td>
<td align="center"><img src="https://skillicons.dev/icons?i=flask" width="48" alt="Flask"/><br/><b>Flask</b></td>
</tr>
<tr><th colspan="3" align="center">🗄️ DATABASES</th></tr>
<tr>
<td align="center"><img src="https://skillicons.dev/icons?i=mysql" width="48" alt="MySQL"/><br/><b>MySQL</b></td>
<td align="center"><img src="https://skillicons.dev/icons?i=mongodb" width="48" alt="MongoDB"/><br/><b>MongoDB</b></td>
<td align="center"><img src="https://skillicons.dev/icons?i=sqlite" width="48" alt="SQLite"/><br/><b>SQLite</b></td>
</tr>
<tr><th colspan="3" align="center">🛠️ TOOLS & PLATFORMS</th></tr>
<tr>
<td align="center"><img src="https://skillicons.dev/icons?i=git" width="48" alt="Git"/><br/><b>Git</b></td>
<td align="center"><img src="https://skillicons.dev/icons?i=github" width="48" alt="GitHub"/><br/><b>GitHub</b></td>
<td align="center"><img src="https://skillicons.dev/icons?i=vscode" width="48" alt="VS Code"/><br/><b>VS Code</b></td>
</tr>
</table>

</div>
'''
readme = readme[:start] + tech + readme[end:]

# Replace profile card with S on the left and terminal details on the right.
start = readme.index("## 🖥️ `SANTHOSH@DEVELOPER:~$ whoami`")
end = readme.index("\n---\n\n## 👨‍💻 ABOUT ME", start)

profile = r'''<div align="center">

## 🖥️ `SANTHOSH@DEVELOPER:~$ whoami`

<table>
<tr>
<td align="center" valign="middle" width="28%">

<img src="https://capsule-render.vercel.app/api?type=transparent&height=190&text=S&fontSize=145&fontColor=58A6FF&animation=fadeIn&desc=DEVELOPER&descSize=12&descAlignY=92" width="190" alt="S developer monogram"/>

</td>
<td align="left" valign="middle" width="72%">

```bash
$ whoami
Santhoshkumar R

$ education
B.Sc. Computer Science Student

$ location
Coimbatore, Tamil Nadu, India

$ role
Aspiring Software Developer

$ tech_stack
Java | Python | JavaScript
React | Node.js | Express

$ databases
MySQL | MongoDB | SQLite

$ focus
Core Java | DSA | SQL | Full Stack Projects

$ goal
Software Engineer / Full Stack Developer

$ philosophy
Learn -> Build -> Test -> Debug -> Improve
```

</td>
</tr>
</table>

</div>

<details>
<summary><b>⌨️ Open developer terminal — quick profile</b></summary>

```text
┌────────────────────── SANTHOSH.DEV ──────────────────────┐
│  USER       : Santhoshkumar R                            │
│  EDUCATION  : B.Sc. Computer Science                     │
│  LOCATION   : Coimbatore, Tamil Nadu, India               │
│  STACK      : Java, Python, JavaScript, React, Node.js   │
│  DATABASES  : MySQL, MongoDB, SQLite                     │
│  FOCUS      : Core Java, DSA, SQL, Full Stack            │
│  GOAL       : Software Engineer                          │
└───────────────────────────────────────────────────────────┘
```

</details>
'''
readme = readme[:start] + profile + readme[end:]

# Center the remaining main section content and ensure generated output path.
out = Path("/mnt/data/README_Santhosh_Centered_3Column.md")
out.write_text(readme, encoding="utf-8")
print(f"Created {out} ({len(readme.splitlines())} lines)")
