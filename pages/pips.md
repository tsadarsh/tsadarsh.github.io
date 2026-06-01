---
layout: default
title: Pressure Injury Prevention System (PIPS 2.0)
permalink: /projects/pips/
---

<div class="pips-container">
  <div class="pips-blueprint-bg">
    
    <!-- Project Title -->
    <h1 class="pips-title" id="pipsTitle">Pressure Injury Prevention System 2.0</h1>
    
    <!-- Project Overview (Default View) -->
    <div id="projectOverview" class="pips-content active">
      <p class="pips-description">
        Originally prototyped as the Pressure Ulcer Prevention System (PUPS), this technology has evolved into PIPS 2.0—a paradigm shift toward continuous, unobtrusive, and data-driven patient monitoring. 
      </p>
      
      <p class="pips-description">
        The system integrates an advanced smart fabric sensor network directly into a fitted mattress sheet, capable of mapping localized pressure magnitudes and microclimate moisture variations in real-time. The data from this piezoresistive sensor matrix is processed through a robust, multi-layered IoT architecture, translating raw analog signals into actionable clinical interventions.
      </p>
      
      <p class="pips-description">
        My work spans the complete hardware-to-software pipeline: designing flexible and rigid PCBs, developing embedded firmware for data acquisition and transmission, and building a Python backend for aggregation, compensation algorithms, and cloud integration.
      </p>
    </div>
    
    <!-- Contribution Tabs -->
    <div class="pips-tabs-wrapper">
      <div class="pips-tabs">
        <button class="pips-tab-btn" data-tab="pcb-design">
          <span class="tab-icon">⚙️</span>
          <span class="tab-label">PCB Design</span>
        </button>
        <button class="pips-tab-btn" data-tab="firmware">
          <span class="tab-icon">💾</span>
          <span class="tab-label">Firmware</span>
        </button>
        <button class="pips-tab-btn" data-tab="backend">
          <span class="tab-icon">🔌</span>
          <span class="tab-label">Backend Software</span>
        </button>
      </div>
    </div>
    
    <!-- Tab Content -->
    <div class="pips-tab-content">
      
      <!-- PCB Design Tab -->
      <div id="pcb-design" class="pips-tab-pane">
        <h2>PCB Design</h2>
        <p>
          I designed two complementary PCBs that form the hardware backbone of PIPS 2.0:
        </p>
        
        <h3>Flexible PCB for Sensor Integration</h3>
        <p>
          This flexible PCB is sewn directly onto the textile material containing the pressure and moisture sensors. The flexible design allows the PCB to conform to the sensor matrix geometry without introducing mechanical stress. It features optimized routing to minimize cross-talk between analog sensor signals, ensuring clean data acquisition from the piezoresistive array.
        </p>
        
        <h3>Main Acquisition Board</h3>
        <p>
          A four-layer rigid PCB serves as the data acquisition hub. It houses an ESP32 microcontroller that gathers analog data from one section of the sensor mat through flexible PCBs. The board includes signal conditioning circuitry for filtering and amplification, ensuring robust analog-to-digital conversion. Communication with the central Raspberry Pi occurs over I2C, allowing multiple acquisition boards to operate simultaneously on the same bus for scalability.
        </p>
        
        <p>
          Key design considerations: impedance matching, thermal management, and noise isolation between analog and digital domains.
        </p>
      </div>
      
      <!-- Firmware Tab -->
      <div id="firmware" class="pips-tab-pane">
        <h2>Firmware for ESP32 Microcontroller</h2>
        <p>
          I developed embedded firmware for the ESP32 that handles real-time sensor data acquisition with dual transmission modes:
        </p>
        
        <h3>Data Acquisition Pipeline</h3>
        <p>
          The firmware implements a high-frequency ADC sampling routine that continuously reads the pressure and moisture sensor values at configurable intervals. Raw analog data undergoes preliminary buffering and timestamping for accurate temporal correlation in downstream processing.
        </p>
        
        <h3>Dual Transmission Modes</h3>
        <p>
          <strong>I2C Mode (Primary):</strong> Sends processed sensor data to the Raspberry Pi over I2C protocol. The ESP32 acts as an I2C slave device, making it queryable by the central controller. This mode enables tight synchronization and centralized data management.
        </p>
        
        <p>
          <strong>BLE Mode (Secondary):</strong> Provides an alternative wireless transmission path using Bluetooth Low Energy. This enables direct communication with mobile devices or backup connectivity if I2C fails, adding resilience to the system.
        </p>
        
        <p>
          The firmware also implements error handling, watchdog timers, and power management features to ensure long-term reliability in a clinical environment.
        </p>
      </div>
      
      <!-- Backend Software Tab -->
      <div id="backend" class="pips-tab-pane">
        <h2>Backend Software - Python Server</h2>
        <p>
          I built a Python-based backend server that aggregates data from multiple ESP32 microcontrollers and orchestrates the complete data pipeline:
        </p>
        
        <h3>Multi-Device Data Aggregation</h3>
        <p>
          The server communicates with multiple ESP32 acquisition boards simultaneously over I2C, collecting sensor data at regular intervals. It manages device discovery, connection health monitoring, and automatic reconnection logic to handle network disruptions gracefully.
        </p>
        
        <h3>Compensation Algorithms</h3>
        <p>
          Raw sensor data contains artifacts from thermal drift, sensor aging, and environmental factors. I implemented sophisticated compensation algorithms that apply calibration corrections and normalization to transform raw readings into clinically meaningful pressure and moisture values. These algorithms are continuously refined based on ground-truth measurements.
        </p>
        
        <h3>Data Logging and Firebase Integration</h3>
        <p>
          The server maintains local data logs for offline resilience and redundancy. Processed data is pushed to Firebase in real-time, enabling cloud storage, remote monitoring, and integration with clinical dashboards. The architecture supports historical queries and statistical analysis for long-term patient monitoring trends.
        </p>
        
        <p>
          Additional features include API endpoints for configuration, data export, and system diagnostics to support clinical integration and research workflows.
        </p>
      </div>
      
    </div>
    
    <!-- System Architecture Section -->
    <div class="pips-architecture">
      <h2>System Architecture</h2>
      <img src="/assets/images/pips-architecture-placeholder.png" alt="PIPS 2.0 System Architecture Diagram" class="architecture-image">
      <p class="architecture-note">System block diagram showing sensor matrix integration, ESP32 acquisition boards, Raspberry Pi coordinator, and Firebase cloud backend.</p>
    </div>
    
  </div>
</div>

<style>
  .pips-container {
    width: 100%;
    margin: 0;
    padding: 0;
  }
  
  .pips-blueprint-bg {
    background: linear-gradient(135deg, #0a1929 0%, #132f4c 100%);
    background-attachment: fixed;
    position: relative;
    padding: 60px 40px;
    min-height: 100vh;
    overflow-x: hidden;
  }
  
  /* Blueprint grid pattern */
  .pips-blueprint-bg::before {
    content: '';
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: 
      linear-gradient(0deg, transparent 24%, rgba(0, 200, 255, 0.05) 25%, rgba(0, 200, 255, 0.05) 26%, transparent 27%, transparent 74%, rgba(0, 200, 255, 0.05) 75%, rgba(0, 200, 255, 0.05) 76%, transparent 77%, transparent),
      linear-gradient(90deg, transparent 24%, rgba(0, 200, 255, 0.05) 25%, rgba(0, 200, 255, 0.05) 26%, transparent 27%, transparent 74%, rgba(0, 200, 255, 0.05) 75%, rgba(0, 200, 255, 0.05) 76%, transparent 77%, transparent);
    background-size: 50px 50px;
    pointer-events: none;
    z-index: 0;
  }
  
  .pips-blueprint-bg > * {
    position: relative;
    z-index: 1;
  }
  
  .pips-title {
    text-align: center;
    font-size: 3.5rem;
    font-weight: 800;
    color: #00d4ff;
    text-shadow: 0 0 20px rgba(0, 212, 255, 0.3);
    margin: 0 0 40px 0;
    cursor: pointer;
    font-family: 'Courier New', monospace;
    letter-spacing: 2px;
    transition: all 0.3s ease;
  }
  
  .pips-title:hover {
    text-shadow: 0 0 30px rgba(0, 212, 255, 0.6);
    transform: scale(1.02);
  }
  
  .pips-content {
    background: rgba(10, 25, 41, 0.7);
    border: 2px solid rgba(0, 200, 255, 0.3);
    border-radius: 8px;
    padding: 30px;
    margin-bottom: 40px;
    opacity: 0;
    max-height: 0;
    overflow: hidden;
    transition: opacity 0.4s ease, max-height 0.4s ease;
  }
  
  .pips-content.active {
    opacity: 1;
    max-height: 500px;
  }
  
  .pips-description {
    color: #e0e0e0;
    font-size: 1rem;
    line-height: 1.7;
    margin: 15px 0;
  }
  
  .pips-tabs-wrapper {
    display: flex;
    justify-content: center;
    margin-bottom: 30px;
  }
  
  .pips-tabs {
    display: flex;
    gap: 15px;
    flex-wrap: wrap;
    justify-content: center;
  }
  
  .pips-tab-btn {
    background: rgba(0, 200, 255, 0.1);
    border: 2px solid rgba(0, 200, 255, 0.3);
    color: #00d4ff;
    padding: 12px 24px;
    border-radius: 6px;
    cursor: pointer;
    font-size: 0.95rem;
    font-weight: 600;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 8px;
    font-family: 'Courier New', monospace;
    letter-spacing: 1px;
  }
  
  .pips-tab-btn:hover {
    background: rgba(0, 200, 255, 0.2);
    box-shadow: 0 0 15px rgba(0, 200, 255, 0.3);
    transform: translateY(-2px);
  }
  
  .pips-tab-btn.active {
    background: rgba(0, 200, 255, 0.3);
    border-color: rgba(0, 212, 255, 0.8);
    box-shadow: 0 0 20px rgba(0, 212, 255, 0.4);
    text-shadow: 0 0 10px rgba(0, 212, 255, 0.5);
  }
  
  .tab-icon {
    font-size: 1.2rem;
  }
  
  .pips-tab-content {
    background: rgba(10, 25, 41, 0.7);
    border: 2px solid rgba(0, 200, 255, 0.3);
    border-radius: 8px;
    padding: 40px;
    margin-bottom: 40px;
    min-height: 300px;
  }
  
  .pips-tab-pane {
    display: none;
    opacity: 0;
    animation: fadeIn 0.4s ease forwards;
  }
  
  .pips-tab-pane.active {
    display: block;
  }
  
  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(10px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  .pips-tab-pane h2 {
    color: #00d4ff;
    font-size: 2rem;
    margin-top: 0;
    margin-bottom: 20px;
    font-family: 'Courier New', monospace;
    letter-spacing: 1px;
  }
  
  .pips-tab-pane h3 {
    color: #00d4ff;
    font-size: 1.3rem;
    margin-top: 25px;
    margin-bottom: 12px;
    opacity: 0.9;
  }
  
  .pips-tab-pane p {
    color: #e0e0e0;
    font-size: 0.95rem;
    line-height: 1.7;
    margin: 12px 0;
  }
  
  .pips-architecture {
    background: rgba(10, 25, 41, 0.7);
    border: 2px solid rgba(0, 200, 255, 0.3);
    border-radius: 8px;
    padding: 40px;
    text-align: center;
  }
  
  .pips-architecture h2 {
    color: #00d4ff;
    font-size: 2rem;
    margin-top: 0;
    margin-bottom: 30px;
    font-family: 'Courier New', monospace;
    letter-spacing: 1px;
  }
  
  .architecture-image {
    max-width: 100%;
    height: auto;
    border: 2px solid rgba(0, 200, 255, 0.2);
    border-radius: 6px;
    margin-bottom: 15px;
    background: rgba(0, 200, 255, 0.05);
    padding: 20px;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
  
  .architecture-note {
    color: rgba(224, 224, 224, 0.7);
    font-size: 0.9rem;
    font-style: italic;
    margin-top: 15px;
  }
  
  /* Responsive */
  @media (max-width: 768px) {
    .pips-blueprint-bg {
      padding: 40px 20px;
    }
    
    .pips-title {
      font-size: 2.2rem;
      margin-bottom: 30px;
    }
    
    .pips-tab-btn {
      font-size: 0.85rem;
      padding: 10px 16px;
    }
    
    .pips-tab-content {
      padding: 25px;
      min-height: auto;
    }
    
    .pips-architecture {
      padding: 25px;
    }
  }
</style>

<script>
  (function() {
    const titleElement = document.getElementById('pipsTitle');
    const projectOverview = document.getElementById('projectOverview');
    const tabButtons = document.querySelectorAll('.pips-tab-btn');
    const tabPanes = document.querySelectorAll('.pips-tab-pane');
    
    // Initialize
    projectOverview.classList.add('active');
    
    // Tab click handlers
    tabButtons.forEach(button => {
      button.addEventListener('click', function() {
        const tabId = this.getAttribute('data-tab');
        
        // Update active tab button
        tabButtons.forEach(btn => btn.classList.remove('active'));
        this.classList.add('active');
        
        // Hide project overview
        projectOverview.classList.remove('active');
        
        // Update tab panes
        tabPanes.forEach(pane => pane.classList.remove('active'));
        const activePane = document.getElementById(tabId);
        if (activePane) {
          activePane.classList.add('active');
        }
      });
    });
    
    // Title click to reset
    titleElement.addEventListener('click', function() {
      // Remove active state from tabs
      tabButtons.forEach(btn => btn.classList.remove('active'));
      tabPanes.forEach(pane => pane.classList.remove('active'));
      
      // Show project overview
      projectOverview.classList.add('active');
    });
  })();
</script>
