<script setup lang="ts">
import { ref } from 'vue'

</script>

<template>
  <!-- Header -->
  <h1>Karthik.P Resume</h1>

  <div class="header_row">
      <!-- DP Image -->
      <img class="dp_image" src="/pk_10.jpg" alt="DP" />

      <!-- Paragraph -->
      <p class="header_bio">
        Specialist in, <br />
        - AUTOSAR and Bosch Motoronic CAN/ Eth Diagnostic stack <br />
        - Diagnostic protocols UDSonCAN, GMLAN (GMW3110), OBDonCAN (ISO 15031), <br />
        - OBDonUDS (SAE J1979-2), DoIP (ISO 13400) <br />
      </p>
  </div>

  <h2>Work Experience</h2>
  <h3>Bosch Global Software Technologies <br />
      2012 - present</h3>

  <!-- Experience table -->
  <table class="resume_table">
    <thead>
      <tr>
          <th>Role</th>
          <th>Duration</th>
          <th>Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Technical Specialist</td>
          <td>Sep 2025 – Present<br />(7 mos)</td>
          <td>Implementation of Diagnostic stack (CAN &amp; Eth) in High Performance Computer as part of SDV.</td>
        </tr>
        <tr>
          <td>Technical Lead</td>
          <td>Dec 2023 – Aug 2025<br />(1 yr 9 mos)</td>
          <td>
            For Maybach projects:<br />
            - Functional System Co-ordinator for OBDonUDS (SAE J1979-2) modules.<br />
            - Requirement clarification, test planning, top level requirement analysis, design preparation.<br />
            - System testing &amp; joint acceptance testing with Maybach.<br />
            - Expertise in Maybach specific OBDonUDS implementation in Bosch Proprietary Software Architecture.<br />
            -  Also responsible for the cost estimations and Failure Mode & Effects Analysis (FMEA).
          </td>
        </tr>
        <tr>
          <td>Technical Lead</td>
          <td>Oct 2023 – Dec 2023<br />(3 mos)</td>
          <td>BMW projects: Development of own CAN stack on ECU side and a Python based tool on Tester side as a replacement of BOSCH internal tool.</td>
        </tr>
        <tr>
          <td>Technical Lead</td>
          <td>Feb 2023 – Sep 2023<br />(8 mos)</td>
          <td>
            For Software Defined Vehicle:<br />
            - Implemented CAN stack and IPC for TI's SoC TDA4VM.<br />
            - Implemented QNX Hypervisor for Linux Based CAN Datalogger &amp; QNX based Gateway Functionality.
          </td>
        </tr>
        <tr>
          <td>Senior Software Engineer</td>
          <td>Mar 2016 – Jan 2023<br />(6 yrs 11 mos)</td>
          <td>
            For General Motors projects:<br />
              - Project system designer for GM (General Motors) Global B ECM (Engine Control Module) projects <br />
              -Expertise in implementation of <br />
              GM specific requirements in UDSonCAN (Unified Diagnostic Services on Controller Area Network) and <br />
              GMLAN (General Motors Local Area Network) in AUTOSAR architecture
          </td>
        </tr>
        <tr>
          <td>Software Developer</td>
          <td>Jul 2012 – Feb 2016<br />(3 yrs 8 mos)</td>
          <td>
            For Jaguar Land Rover projects:<br />
            - Developer of off-board diagnostic requirements in Bosch's in-house software architecture.<br />
            - Developer of automated code generator based on Perl platform.<br />
            - Python based test automation for all diagnostic services.
          </td> 
        </tr>
      </tbody>
  </table>




  </template>
<style scoped>

/* To have all the font in MAC format */
* {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
}

/* Header styles */
h1 {
  text-align: center;
  margin-bottom: 2rem;
}

.header_row {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header_bio {
  flex: 1;        /* takes up remaining space on the left */
  margin-right: 1rem;
}

.dp_image {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 150px;
  height: 150px;
  border-radius: 50%;
  flex-shrink: 0; /* prevents image from being squished */
}

/* Table styles */
.resume_table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 2rem;
}

.resume_table th,
.resume_table td {
  border: 1px solid #d1d1d1;
  padding: 8px 12px;
  text-align: left;
}

.resume_table th {
  background-color: #f0f0f0;
  font-weight: 600;
}

.resume_table tr:nth-child(even) {
  background-color: #f9f9f9;
}

</style>
