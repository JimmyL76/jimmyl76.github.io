<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name - VLSI Design Engineer</title>
    <style>
        :root {
            --bg-primary: #0a0e1a;
            --bg-secondary: #1a1f2e;
            --bg-tertiary: #252b3d;
            --text-primary: #e1e8f0;
            --text-secondary: #8892b0;
            --accent: #4fc3f7;
            --accent-hover: #29b6f6;
            --green: #66bb6a;
            --purple: #ab47bc;
            --orange: #ff7043;
            --red: #ef5350;
            --yellow: #ffca28;
            --border: #2d3748;
            --shadow: rgba(0, 0, 0, 0.4);
            --gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'JetBrains Mono', 'Fira Code', 'SF Mono', 'Consolas', monospace;
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animated background circuit pattern */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(79, 195, 247, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(171, 71, 188, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(255, 112, 67, 0.03) 0%, transparent 50%);
            z-index: -1;
        }

        /* Terminal cursor animation */
        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        .cursor {
            display: inline-block;
            background-color: var(--accent);
            width: 2px;
            height: 1.2em;
            animation: blink 1s infinite;
            margin-left: 2px;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 14, 26, 0.95);
            backdrop-filter: blur(15px);
            z-index: 1000;
            border-bottom: 1px solid var(--border);
        }

        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
            padding: 1rem 0;
            gap: 2rem;
        }

        nav a {
            color: var(--text-secondary);
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 0.9rem;
            padding: 0.5rem 1rem;
            border-radius: 4px;
        }

        nav a:hover,
        nav a.active {
            color: var(--accent);
            background: rgba(79, 195, 247, 0.1);
        }

        /* Main container */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Sections */
        section {
            min-height: 100vh;
            padding: 6rem 0 2rem;
            display: flex;
            align-items: center;
        }

        .section-content {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 20%;
            left: 50%;
            transform: translateX(-50%);
            width: 300px;
            height: 300px;
            background: var(--gradient);
            border-radius: 50%;
            opacity: 0.1;
            filter: blur(100px);
            z-index: -1;
        }

        .terminal-window {
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            border-radius: 12px;
            margin: 2rem 0;
            overflow: hidden;
            box-shadow: 0 20px 40px var(--shadow);
            position: relative;
        }

        .terminal-window::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: var(--gradient);
        }

        .terminal-header {
            background: var(--bg-tertiary);
            padding: 0.8rem 1.5rem;
            display: flex;
            align-items: center;
            gap: 0.8rem;
        }

        .terminal-dots {
            display: flex;
            gap: 0.5rem;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .dot.red { background: var(--red); }
        .dot.yellow { background: var(--yellow); }
        .dot.green { background: var(--green); }

        .terminal-title {
            margin-left: 1rem;
            font-size: 0.85rem;
            color: var(--text-secondary);
        }

        .terminal-body {
            padding: 2rem;
            font-size: 0.95rem;
        }

        .prompt {
            color: var(--green);
        }

        .command {
            color: var(--accent);
        }

        .output {
            color: var(--text-primary);
            margin: 0.5rem 0;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin: 2rem 0 1rem;
            background: var(--gradient);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 200% 200%;
            animation: gradient 4s ease infinite;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .hero .subtitle {
            font-size: 1.3rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
        }

        .hero .specialization {
            display: inline-block;
            background: rgba(79, 195, 247, 0.1);
            color: var(--accent);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
            margin-top: 1rem;
            border: 1px solid rgba(79, 195, 247, 0.3);
        }

        /* About Section */
        .about {
            background: var(--bg-secondary);
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: start;
        }

        .about-text h2 {
            color: var(--accent);
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            position: relative;
        }

        .about-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 3px;
            background: var(--gradient);
            border-radius: 2px;
        }

        .about-text p {
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            font-size: 1.05rem;
        }

        .skills-section {
            margin-top: 2rem;
        }

        .skills-category {
            margin-bottom: 2rem;
        }

        .skills-category h3 {
            color: var(--purple);
            font-size: 1.1rem;
            margin-bottom: 0.8rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem;
        }

        .skill-tag {
            background: var(--bg-tertiary);
            color: var(--text-primary);
            padding: 0.4rem 0.9rem;
            border-radius: 6px;
            font-size: 0.85rem;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
            position: relative;
        }

        .skill-tag:hover {
            border-color: var(--accent);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(79, 195, 247, 0.2);
        }

        .verilog-code {
            background: var(--bg-primary);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.8rem;
            position: relative;
            overflow: hidden;
        }

        .verilog-code::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--green), var(--purple));
        }

        .code-header {
            color: var(--text-secondary);
            font-size: 0.85rem;
            margin-bottom: 1.2rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .code-line {
            margin: 0.4rem 0;
            position: relative;
        }

        .line-number {
            color: var(--text-secondary);
            margin-right: 1.5rem;
            user-select: none;
            width: 25px;
            display: inline-block;
        }

        .keyword { color: var(--purple); font-weight: 600; }
        .string { color: var(--green); }
        .function { color: var(--orange); }
        .comment { color: var(--text-secondary); font-style: italic; }
        .number { color: var(--yellow); }

        /* Projects Section */
        .projects h2 {
            color: var(--accent);
            font-size: 2.2rem;
            margin-bottom: 3rem;
            text-align: center;
            position: relative;
        }

        .projects h2::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: var(--gradient);
            border-radius: 2px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 2.5rem;
            margin-top: 3rem;
        }

        .project-card {
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2rem;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--gradient);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.4s ease;
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        .project-card:hover {
            transform: translateY(-8px);
            border-color: var(--accent);
            box-shadow: 0 15px 35px var(--shadow);
        }

        .project-type {
            display: inline-block;
            background: rgba(171, 71, 188, 0.2);
            color: var(--purple);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-bottom: 1rem;
            border: 1px solid rgba(171, 71, 188, 0.3);
        }

        .project-title {
            color: var(--accent);
            font-size: 1.4rem;
            margin-bottom: 0.8rem;
            font-weight: 600;
        }

        .project-desc {
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            line-height: 1.7;
        }

        .project-specs {
            background: var(--bg-tertiary);
            padding: 1rem;
            border-radius: 8px;
            margin: 1rem 0;
            border-left: 3px solid var(--green);
        }

        .project-specs h4 {
            color: var(--green);
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }

        .spec-item {
            display: flex;
            justify-content: space-between;
            margin: 0.3rem 0;
            font-size: 0.85rem;
        }

        .spec-label {
            color: var(--text-secondary);
        }

        .spec-value {
            color: var(--text-primary);
            font-weight: 500;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.4rem;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background: var(--bg-tertiary);
            color: var(--text-primary);
            padding: 0.3rem 0.7rem;
            border-radius: 4px;
            font-size: 0.75rem;
            border: 1px solid var(--border);
        }

        .project-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .project-link {
            color: var(--accent);
            text-decoration: none;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1rem;
            border: 1px solid rgba(79, 195, 247, 0.3);
            border-radius: 6px;
        }

        .project-link:hover {
            color: var(--accent-hover);
            background: rgba(79, 195, 247, 0.1);
            transform: translateY(-2px);
        }

        /* Education & Experience */
        .experience {
            background: var(--bg-secondary);
        }

        .timeline {
            position: relative;
            margin: 2rem 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 30px;
            top: 0;
            bottom: 0;
            width: 2px;
            background: var(--gradient);
        }

        .timeline-item {
            position: relative;
            padding-left: 80px;
            margin-bottom: 2rem;
        }

        .timeline-dot {
            position: absolute;
            left: 22px;
            top: 8px;
            width: 16px;
            height: 16px;
            background: var(--accent);
            border-radius: 50%;
            border: 3px solid var(--bg-secondary);
        }

        .timeline-content {
            background: var(--bg-tertiary);
            padding: 1.5rem;
            border-radius: 8px;
            border: 1px solid var(--border);
        }

        .timeline-title {
            color: var(--accent);
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }

        .timeline-org {
            color: var(--purple);
            margin-bottom: 0.5rem;
        }

        .timeline-period {
            color: var(--text-secondary);
            font-size: 0.85rem;
            margin-bottom: 1rem;
        }

        /* Contact Section */
        .contact {
            text-align: center;
        }

        .contact h2 {
            color: var(--accent);
            font-size: 2.2rem;
            margin-bottom: 2rem;
            position: relative;
        }

        .contact h2::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: var(--gradient);
            border-radius: 2px;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .contact-card {
            background: var(--bg-secondary);
            padding: 2rem;
            border-radius: 12px;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
            text-decoration: none;
            color: var(--text-primary);
        }

        .contact-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            box-shadow: 0 10px 25px var(--shadow);
        }

        .contact-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
            display: block;
        }

        .contact-label {
            font-size: 1.1rem;
            color: var(--accent);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 0 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .about-grid {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            nav ul {
                gap: 1rem;
                flex-wrap: wrap;
                padding: 0.8rem 0;
            }

            nav a {
                font-size: 0.8rem;
                padding: 0.3rem 0.6rem;
            }

            .timeline::before {
                left: 15px;
            }

            .timeline-item {
                padding-left: 50px;
            }

            .timeline-dot {
                left: 7px;
            }
        }

        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <ul>
            <li><a href="#home" class="active">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#experience">Experience</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container">
            <div class="section-content">
                <div class="terminal-window">
                    <div class="terminal-header">
                        <div class="terminal-dots">
                            <div class="dot red"></div>
                            <div class="dot yellow"></div>
                            <div class="dot green"></div>
                        </div>
                        <div class="terminal-title">vlsi_terminal — EDA_workspace — 120x40</div>
                    </div>
                    <div class="terminal-body">
                        <div class="code-line">
                            <span class="prompt">designer@workstation:~/projects$</span> 
                            <span class="command">cat profile.txt</span>
                        </div>
                        <div class="output">VLSI Design Engineer | Digital IC Designer</div>
                        <div class="code-line">
                            <span class="prompt">designer@workstation:~/projects$</span> 
                            <span class="command">ls -la tools/</span>
                        </div>
                        <div class="output">Verilog  SystemVerilog  Cadence  Synopsys  Xilinx  SPICE</div>
                        <div class="code-line">
                            <span class="prompt">designer@workstation:~/projects$</span> 
                            <span class="command">grep -r "passion" *.md</span>
                        </div>
                        <div class="output">Building efficient, low-power digital systems from RTL to silicon<span class="cursor"></span></div>
                    </div>
                </div>
                <h1>Your Name</h1>
                <p class="subtitle">VLSI Design Engineer specializing in digital IC design, verification, and physical implementation</p>
                <div class="specialization">🔬 Digital Design • 🧪 Verification • 🔌 Low-Power Design</div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="section-content">
                <div class="about-grid">
                    <div class="about-text">
                        <h2>// About Me</h2>
                        <p>I'm a VLSI design engineer passionate about creating efficient digital systems from concept to silicon. My expertise spans the entire IC design flow, from RTL coding and verification to physical design and timing closure.</p>
                        <p>I love tackling complex design challenges, optimizing for power and performance, and working with cutting-edge EDA tools. Currently seeking internship opportunities to apply my skills in real-world chip design projects.</p>
                        
                        <div class="skills-section">
                            <div class="skills-category">
                                <h3>🔧 Hardware Description Languages</h3>
                                <div class="skills">
                                    <span class="skill-tag">Verilog</span>
                                    <span class="skill-tag">SystemVerilog</span>
                                    <span class="skill-tag">VHDL</span>
                                    <span class="skill-tag">SystemC</span>
                                </div>
                            </div>
                            
                            <div class="skills-category">
                                <h3>⚙️ EDA Tools</h3>
                                <div class="skills">
                                    <span class="skill-tag">Cadence Innovus</span>
                                    <span class="skill-tag">Synopsys DC</span>
                                    <span class="skill-tag">Xilinx Vivado</span>
                                    <span class="skill-tag">ModelSim/QuestaSim</span>
                                    <span class="skill-tag">Magic</span>
                                    <span class="skill-tag">OpenROAD</span>
                                </div>
                            </div>
                            
                            <div class="skills-category">
                                <h3>📊 Specializations</h3>
                                <div class="skills">
                                    <span class="skill-tag">RTL Design</span>
                                    <span class="skill-tag">Design Verification</span>
                                    <span class="skill-tag">Physical Design</span>
                                    <span class="skill-tag">Low-Power Design</span>
                                    <span class="skill-tag">FPGA Prototyping</span>
                                    <span class="skill-tag">DFT</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="verilog-code">
                        <div class="code-header">
                            <span>📄 cpu_pipeline.sv</span>
                        </div>
                        <div class="code-line">
                            <span class="line-number">1</span>
                            <span class="keyword">module</span> <span class="function">cpu_pipeline</span> (
                        </div>
                        <div class="code-line">
                            <span class="line-number">2</span>
                            <span class="keyword">  input</span> clk, rst_n,
                        </div>
                        <div class="code-line">
                            <span class="line-number">3</span>
                            <span class="keyword">  input</span> [<span class="number">31</span>:<span class="number">0</span>] instruction,
                        </div>
                        <div class="code-line">
                            <span class="line-number">4</span>
                            <span class="keyword">  output</span> [<span class="number">31</span>:<span class="number">0</span>] result
                        </div>
                        <div class="code-line">
                            <span class="line-number">5</span>
                            );
                        </div>
                        <div class="code-line">
                            <span class="line-number">6</span>
                            <span class="comment">  // Pipeline stages: IF -> ID -> EX -> MEM -> WB</span>
                        </div>
                        <div class="code-line">
                            <span class="line-number">7</span>
                            <span class="keyword">  logic</span> [<span class="number">31</span>:<span class="number">0</span>] if_pc, id_instr;
                        </div>
                        <div class="code-line">
                            <span class="line-number">8</span>
                            <span class="keyword">  logic</span> [<span class="number">4</span>:<span class="number">0</span>] ex_alu_op;
                        </div>
                        <div class="code-line">
                            <span class="line-number">9</span>
                            <span class="keyword">  logic</span> mem_write_en, wb_reg_write;
                        </div>
                        <div class="code-line">
                            <span class="line-number">10</span>
                            
                        </div>
                        <div class="code-line">
                            <span class="line-number">11</span>
                            <span class="comment">  // Power-gated execution units</span>
                        </div>
                        <div class="code-line">
                            <span class="line-number">12</span>
                            <span class="keyword">  always_ff</span> @(<span class="keyword">posedge</span> clk) <span class="keyword">begin</span>
                        </div>
                        <div class="code-line">
                            <span class="line-number">13</span>
                            <span class="keyword">    if</span> (power_enable && !stall)
                        </div>
                        <div class="code-line">
                            <span class="line-number">14</span>
                            result <= alu_result;
                        </div>
                        <div class="code-line">
                            <span class="line-number">15</span>
                            <span class="keyword">  end</span>
                        </div>
                        <div class="code-line">
                            <span class="line-number">16</span>
                            <span class="keyword">endmodule</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <div class="container">
            <div class="section-content">
                <h2>// Featured Projects</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-type">RTL Design</div>
                        <h3 class="project-title">RISC-V Processor Core</h3>
                        <p class="project-desc">32-bit RISC-V processor implementation with 5-stage pipeline, hazard detection, and branch prediction. Includes comprehensive verification testbench and FPGA prototyping.</p>
                        
                        <div class="project-specs">
                            <h4>📊 Design Specifications</h4>
                            <div class="spec-item">
                                <span class="spec-label">ISA:</span>
                                <span class="spec-value">RV32I Base + M Extension</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Pipeline Stages:</span>
                                <span class="spec-value">5 (IF, ID, EX, MEM, WB)</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Max Frequency:</span>
                                <span class="spec-value">100 MHz (Xilinx 7-series)</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Area:</span>
                                <span class="spec-value">~15k LUTs, 8k FFs</span>
                            </div>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">SystemVerilog</span>
                            <span class="tech-tag">Vivado</span>
                            <span class="tech-tag">QuestaSim</span>
                            <span class="tech-tag">RISC-V</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">🔗 GitHub</a>
                            <a href="#" class="project-link">📄 Report</a>
                            <a href="#" class="project-link">🎥 Demo</a>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-type">Verification</div>
                        <h3 class="project-title">UVM Testbench for DDR4 Controller</h3>
                        <p class="project-desc">Comprehensive verification environment using UVM methodology for DDR4 memory controller. Achieved 95%+ functional coverage with constrained random testing and directed tests.</p>
                        
                        <div class="project-specs">
                            <h4>🧪 Verification Metrics</h4>
                            <div class="spec-item">
                                <span class="spec-label">Code Coverage:</span>
                                <span class="spec-value">98% Line, 94% Branch</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Functional Coverage:</span>
                                <span class="spec-value">96% Cross-coverage</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Test Cases:</span>
                                <span class="spec-value">500+ Directed + Random</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Bugs Found:</span>
                                <span class="spec-value">12 Critical, 28 Minor</span>
                            </div>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">SystemVerilog</span>
                            <span class="tech-tag">UVM</span>
                            <span class="tech-tag">QuestaSim</span>
                            <span class="tech-tag">DVT Eclipse</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">🔗 GitHub</a>
                            <a href="#" class="project-link">📊 Coverage Report</a>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-type">Analog/Mixed-Signal</div>
                        <h3 class="project-title">Low-Power ADC Design</h3>
                        <p class="project-desc">12-bit SAR ADC design in 65nm CMOS technology with power optimization techniques. Complete analog design from schematic to layout with extensive SPICE simulation.</p>
                        
                        <div class="project-specs">
                            <h4>📈 Performance Metrics</h4>
                            <div class="spec-item">
                                <span class="spec-label">Resolution:</span>
                                <span class="spec-value">12-bit, 4096 levels</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Sample Rate:</span>
                                <span class="spec-value">1 MS/s</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Power:</span>
                                <span class="spec-value">2.1 mW @ 1.2V</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">ENOB:</span>
                                <span class="spec-value">11.2 bits</span>
                            </div>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">Cadence Virtuoso</span>
                            <span class="tech-tag">SPICE</span>
                            <span class="tech-tag">65nm PDK</span>
                            <span class="tech-tag">Python (Analysis)</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">📄 Design Report</a>
                            <a href="#" class="project-link">📊 Simulation Results</a>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-type">Physical Design</div>
                        <h3 class="project-title">ARM Cortex-M0 Implementation</h3>
                        <p class="project-desc">Complete physical design implementation of ARM Cortex-M0 processor using open-source tools. Includes floor planning, placement, CTS, and routing with timing closure.</p>
                        
                        <div class="project-specs">
                            <h4>🔧 Implementation Results</h4>
                            <div class="spec-item">
                                <span class="spec-label">Technology:</span>
                                <span class="spec-value">SkyWater 130nm PDK</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Core Area:</span>
                                <span class="spec-value">0.085 mm²</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Max Frequency:</span>
                                <span class="spec-value">50 MHz</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Utilization:</span>
                                <span class="spec-value">72% core, 45% total</span>
                            </div>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">OpenROAD</span>
                            <span class="tech-tag">Magic</span>
                            <span class="tech-tag">Netgen</span>
                            <span class="tech-tag">SkyWater 130nm</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">🔗 GitHub</a>
                            <a href="#" class="project-link">📐 Layout View</a>
                            <a href="#" class="project-link">📊 PPA Report</a>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-type">FPGA</div>
                        <h3 class="project-title">CNN Accelerator on FPGA</h3>
                        <p class="project-desc">Hardware accelerator for convolutional neural networks implemented on Xilinx FPGA. Features optimized MAC units, systolic array architecture, and custom memory hierarchy.</p>
                        
                        <div class="project-specs">
                            <h4>⚡ Performance Results</h4>
                            <div class="spec-item">
                                <span class="spec-label">Platform:</span>
                                <span class="spec-value">Xilinx ZCU102</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Throughput:</span>
                                <span class="spec-value">245 GOPS</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Precision:</span>
                                <span class="spec-value">INT8 Quantized</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Power Efficiency:</span>
                                <span class="spec-value">12.3 GOPS/W</span>
                            </div>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">Verilog</span>
                            <span class="tech-tag">Vivado HLS</span>
                            <span class="tech-tag">Xilinx SDK</span>
                            <span class="tech-tag">Python</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">🔗 GitHub</a>
                            <a href="#" class="project-link">🎯 Benchmarks</a>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-type">System Design</div>
                        <h3 class="project-title">IoT Sensor Node SoC</h3>
                        <p class="project-desc">Ultra-low-power SoC design for IoT applications featuring ARM Cortex-M0+ core, sensor interfaces, wireless connectivity, and advanced power management.</p>
                        
                        <div class="project-specs">
                            <h4>🌐 System Features</h4>
                            <div class="spec-item">
                                <span class="spec-label">Core:</span>
                                <span class="spec-value">ARM Cortex-M0+ @ 32MHz</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Memory:</span>
                                <span class="spec-value">64KB SRAM, 256KB Flash</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Interfaces:</span>
                                <span class="spec-value">SPI, I2C, UART, ADC</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Sleep Power:</span>
                                <span class="spec-value">1.2 µA</span>
                            </div>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">SystemVerilog</span>
                            <span class="tech-tag">ARM AMBA</span>
                            <span class="tech-tag">Power Management</span>
                            <span class="tech-tag">Synthesis</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">📄 Architecture Doc</a>
                            <a href="#" class="project-link">⚡ Power Analysis</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="experience">
        <div class="container">
            <div class="section-content">
                <h2 style="color: var(--accent); font-size: 2.2rem; margin-bottom: 3rem; text-align: center; position: relative;">// Education & Experience</h2>
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <h3 class="timeline-title">M.S. in Electrical Engineering</h3>
                            <div class="timeline-org">University Name</div>
                            <div class="timeline-period">2023 - Present</div>
                            <p style="color: var(--text-secondary);">Specialization in VLSI Design and Computer Architecture. Relevant coursework: Advanced Digital Design, VLSI Testing, Low-Power Design, Computer Architecture.</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <h3 class="timeline-title">Design Verification Intern</h3>
                            <div class="timeline-org">Tech Company / Startup</div>
                            <div class="timeline-period">Summer 2024</div>
                            <p style="color: var(--text-secondary);">Developed UVM testbenches for PCIe controller verification. Improved functional coverage by 15% and identified critical timing violations in high-speed interfaces.</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <h3 class="timeline-title">Research Assistant</h3>
                            <div class="timeline-org">University VLSI Lab</div>
                            <div class="timeline-period">2023 - Present</div>
                            <p style="color: var(--text-secondary);">Research on low-power processor design techniques. Published 2 conference papers on dynamic voltage scaling and power gating methodologies.</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <h3 class="timeline-title">B.S. in Electrical Engineering</h3>
                            <div class="timeline-org">University Name</div>
                            <div class="timeline-period">2019 - 2023</div>
                            <p style="color: var(--text-secondary);">Graduated Magna Cum Laude. Senior Design Project: FPGA-based Digital Signal Processor. IEEE Student Member, Dean's List 6 semesters.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <div class="section-content">
                <h2>// Let's Connect</h2>
                <p style="color: var(--text-secondary); margin-bottom: 3rem; font-size: 1.1rem;">Open to internship opportunities and collaborative projects</p>
                <div class="contact-grid">
                    <a href="mailto:your.email@university.edu" class="contact-card">
                        <span class="contact-icon">📧</span>
                        <div class="contact-label">Email</div>
                        <div style="color: var(--text-secondary); margin-top: 0.5rem;">your.email@university.edu</div>
                    </a>
                    <a href="https://linkedin.com/in/yourprofile" class="contact-card">
                        <span class="contact-icon">💼</span>
                        <div class="contact-label">LinkedIn</div>
                        <div style="color: var(--text-secondary); margin-top: 0.5rem;">Professional Profile</div>
                    </a>
                    <a href="https://github.com/yourusername" class="contact-card">
                        <span class="contact-icon">🔗</span>
                        <div class="contact-label">GitHub</div>
                        <div style="color: var(--text-secondary); margin-top: 0.5rem;">Code & Projects</div>
                    </a>
                    <a href="path/to/your-resume.pdf" class="contact-card">
                        <span class="contact-icon">📄</span>
                        <div class="contact-label">Resume</div>
                        <div style="color: var(--text-secondary); margin-top: 0.5rem;">Download PDF</div>
                    </a>
                </div>
                
                <div style="margin-top: 3rem; padding: 2rem; background: var(--bg-secondary); border-radius: 12px; border: 1px solid var(--border);">
                    <h3 style="color: var(--purple); margin-bottom: 1rem;">🎯 Seeking Opportunities In:</h3>
                    <div style="display: flex; flex-wrap: wrap; gap: 1rem; justify-content: center;">
                        <span class="skill-tag" style="background: rgba(79, 195, 247, 0.1); border-color: var(--accent);">Digital IC Design</span>
                        <span class="skill-tag" style="background: rgba(171, 71, 188, 0.1); border-color: var(--purple);">Design Verification</span>
                        <span class="skill-tag" style="background: rgba(102, 187, 106, 0.1); border-color: var(--green);">Physical Design</span>
                        <span class="skill-tag" style="background: rgba(255, 112, 67, 0.1); border-color: var(--orange);">FPGA Design</span>
                        <span class="skill-tag" style="background: rgba(255, 202, 40, 0.1); border-color: var(--yellow);">Mixed-Signal Design</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Smooth scrolling for navigation
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                target.scrollIntoView({ behavior: 'smooth' });
                
                // Update active nav item
                document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
                this.classList.add('active');
            });
        });

        // Update active nav on scroll
        window.addEventListener('scroll', () => {
            let current = '';
            document.querySelectorAll('section').forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (scrollY >= (sectionTop - 200)) {
                    current = section.getAttribute('id');
                }
            });

            document.querySelectorAll('nav a').forEach(a => {
                a.classList.remove('active');
                if (a.getAttribute('href') === '#' + current) {
                    a.classList.add('active');
                }
            });
        });

        // Terminal typing effect
        const terminalOutputs = document.querySelectorAll('.terminal-body .output');
        terminalOutputs.forEach((output, index) => {
            const text = output.innerHTML;
            output.innerHTML = '';
            setTimeout(() => {
                let i = 0;
                const typeWriter = () => {
                    if (i < text.length) {
                        if (text.charAt(i) === '<') {
                            // Handle HTML tags
                            const tagEnd = text.indexOf('>', i);
                            output.innerHTML += text.substring(i, tagEnd + 1);
                            i = tagEnd + 1;
                        } else {
                            output.innerHTML += text.charAt(i);
                            i++;
                        }
                        setTimeout(typeWriter, 30 + Math.random() * 40);
                    }
                };
                typeWriter();
            }, index * 1200);
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe project cards and timeline items
        document.querySelectorAll('.project-card, .timeline-item').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
