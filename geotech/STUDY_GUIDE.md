# Geotechnical Engineering — Quick Study and Refresh Guide

A short refresher for job applications and interviews. For each topic you get: **what to refresh**, **numbers and equations to know by heart**, **interview questions to practise**, and **where to read** (see [`SOURCES.md`](SOURCES.md)). Section 9 lists **newer topics** that come up in current interviews.

> Typical values below are textbook rules of thumb for checking answers quickly. They are not design values; always use project-specific data and the code that applies.

---

## 0. Four-week refresh plan (about 1 hour/day)

| Week | Focus | Main free reading |
|---|---|---|
| 1 | Soil behaviour, effective stress, consolidation, shear strength, site investigation and CPT | FHWA *Soils & Foundations* Vol. I; MIT 1.361 notes; Robertson & Cabal CPT guide |
| 2 | Shallow and deep foundations, piles, load testing, settlement | FHWA *Soils & Foundations* Vol. II; GEC 10, GEC 12 |
| 3 | Retaining walls, deep excavations, cut-and-cover, anchors, dewatering | C760 summary; GEC 4; FHWA Road Tunnel Manual (cut-and-cover chapter); EM 1110-2-2504 |
| 4 | Tunnelling (SCL/NATM, TBM), rock mechanics, 2nd-gen EC7, digital and new topics | Hoek *Practical Rock Engineering*; ITA WG reports; Crossrail Learning Legacy |

Each week, finish with **one worked problem** from memory and **one case history** you can talk about for 2 minutes.

---

## 1. Soil behaviour and strength

**Refresh**
- Effective stress σ′ = σ − u. Total vs effective stress analysis; drained vs undrained loading (and how loading rate, permeability, and drainage path decide which applies).
- Stress history: OCR, preconsolidation σ′p (Casagrande, work method), K0.
- Consolidation: Terzaghi 1D theory, cv, Cc, Cr, mv; secondary compression Cα; the time-settlement curve.
- Shear strength: Mohr–Coulomb (c′, φ′), undrained strength su, critical state (φ′cs, CSL, e–ln p′), peak vs critical vs residual strength; dilatancy (Bolton 1986).
- Stress paths (MIT s′–t and Cambridge p′–q): how CU, CD, UU, and K0 tests differ.
- Stiffness: strain dependence, G0 from shear-wave velocity (G0 = ρVs²), degradation curves.
- Sensitivity, structure, cementation, partial saturation, swelling and collapsible soils.

**Numbers and equations**
- K0 ≈ 1 − sin φ′ (Jáky, NC); K0,OC ≈ (1 − sin φ′)·OCR^sin φ′ (Mayne & Kulhawy).
- SHANSEP: su/σ′v = S·OCR^m, with S ≈ 0.22 and m ≈ 0.8 for many clays (Ladd).
- Settlement (NC): s = Cc·H/(1+e0)·log(σ′f/σ′0). Time: t = Tv·Hdr²/cv; T50 = 0.197, T90 = 0.848.
- Cα/Cc ≈ 0.04 ± 0.01 for inorganic clays (Mesri).
- Typical φ′cs: clean quartz sand 30–34°; clays drop toward φ′r 8–20° at large displacement.

**Practice questions**
1. Why is short-term (undrained) stability critical for an embankment on soft clay but long-term (drained) stability critical for a cut slope in clay?
2. Explain what pore pressure parameter A tells you about how a soil behaves.
3. How would you get design stiffness for an FE excavation model from SI data?

---

## 2. Site investigation and ground models

**Refresh**
- SI phases: desk study (geology, historical maps, utilities, UXO, previous SI) → walkover → preliminary → main → supplementary/verification during construction.
- Methods: rotary coring (TCR/SCR/RQD), cable percussion, sonic, trial pits; SPT, CPTu, SCPT, DMT, PMT, vane, packer and pumping tests; geophysics (MASW, ERT, seismic refraction, cross-hole).
- Lab: classification (PSD, Atterberg limits), oedometer, triaxial (UU/CU/CD, with Ko consolidation), direct and ring shear, permeability, rock UCS, point load, Brazilian, chemical tests.
- Groundwater: piezometers (standpipe, VWP), seasonal variation, artesian pressures.
- **Ground model chain:** Geological model → Ground model → Geotechnical design model. Reports: factual report (GDR) vs interpretive report (GIR/GIR-type) vs **Geotechnical Baseline Report (GBR)**, which sets contractual baselines.
- Data: the AGS format, borehole databases, 3D models (Leapfrog).

**Numbers and equations**
- SPT: N60 = N·(ER/60); (N1)60 = CN·N60, with CN ≈ (Pa/σ′v)^0.5 ≤ 1.7.
- CPTu: qt = qc + u2(1 − a); su = (qt − σv0)/Nkt, with Nkt ≈ 10–20 (often ~14); soil behaviour type index Ic (Robertson). Ic > ~2.6 usually means clay-like behaviour.
- Investigation depth rules of thumb: footings 1.5–2B below the founding level; piles ≥ 5 pile diameters (or about 3 m) below the toe; tunnels at least one diameter below the invert.

**Practice questions**
1. Plan an SI for a 20 m deep metro station box in an urban area. What would you do, in what order, and why?
2. What is the difference between a GDR, a GIR, and a GBR? Who carries the risk if ground conditions differ from the baseline?
3. CPTu shows qt rising and Bq near zero in one layer. What material is it likely to be?

---

## 3. Shallow foundations

**Refresh**
- Bearing capacity (Terzaghi, Meyerhof, Hansen, Vesić): shape, depth, inclination, and eccentricity factors; effective width B′ = B − 2e.
- Settlement: immediate (elastic), consolidation, secondary; Schmertmann method in sands; Burland & Burbidge method (SPT-based).
- Rafts, compensated foundations, and differential settlement and angular distortion criteria (about 1/500 as a common guide; 1/300 for cracking risk; Skempton & MacDonald; Bjerrum).
- LRFD/Eurocode verification vs allowable stress design.

**Numbers and equations**
- q_ult = c′Nc sc dc + q Nq sq dq + ½γ′B′Nγ sγ dγ.
- Undrained strip: q_ult = (π + 2)su + q = 5.14 su + q; square or circle (Skempton) ≈ 6.2 su at the surface.
- Nq = e^(π tan φ′) tan²(45 + φ′/2); Nc = (Nq − 1) cot φ′.

**Practice questions**
1. Why is bearing capacity rarely the governing check for footings in sand? (Settlement usually governs.)
2. How does a high water table affect bearing capacity?

---

## 4. Deep foundations (piles)

**Refresh**
- Pile types: driven (precast, steel H and tube), bored or drilled shafts, CFA/ACIP, displacement auger, micropiles, barrettes.
- Axial capacity: α-method (total stress), β-method (effective stress), CPT-based methods (LCPC, Unicone, UWA-05, ICP-05 for driven piles in sand); base resistance; **set-up** and relaxation over time.
- Load–settlement: shaft resistance mobilises at about 0.5–1% of D; the base needs about 10% of D. Settlement-based design, t-z and q-z curves.
- Lateral loading: p–y curves (LPILE), Broms method, fixed vs free head.
- Groups: efficiency, block failure, group settlement (equivalent raft method), **piled raft** design.
- Negative skin friction (downdrag), neutral plane (Fellenius).
- Testing: static load test (maintained load, CRP), bi-directional O-cell, dynamic test (PDA/CAPWAP), rapid load test, integrity testing (PIT, CSL, thermal).
- Construction: bentonite or polymer support fluid, concrete tremie, base cleaning, soft toes.

**Numbers and equations**
- Q_ult = Qs + Qb = Σ fs·As + qb·Ab.
- α-method: fs = α·su, with α ≈ 1 for soft clay, decreasing to about 0.5 or less for stiff clay (API / Tomlinson charts). β-method: fs = β·σ′v, β ≈ 0.25–0.4 in clays (Burland); higher in sands.
- Undrained base: qb = 9·su.

**Practice questions**
1. Why might a pile load test show much more capacity three weeks after driving than at the end of driving?
2. A building is to be built on piles through 10 m of fresh fill over soft clay. What special issues apply? (Downdrag, the neutral plane, group settlement.)
3. When would you choose a piled raft over a fully piled foundation?

---

## 5. Retaining walls and deep excavations (incl. cut-and-cover)

**Refresh**
- Earth pressure: Rankine, Coulomb, log-spiral passive; at-rest pressure; compaction pressures; surcharges (Boussinesq).
- Wall types: sheet pile, contiguous, secant (hard/firm, hard/soft), diaphragm walls, soldier pile and lagging, king post, SMW/CSM, soil nail, anchored walls.
- Support: cantilever, propped (single and multi-level), anchored, **top-down vs bottom-up** construction; slabs as props; temperature effects in steel props.
- Design methods: limit equilibrium (free and fixed earth support), beam on springs (WALLAP, Frew), FE (PLAXIS). The C760 approach, Eurocode DA1 Combinations 1 and 2.
- Stability checks: **basal heave** (Terzaghi, Bjerrum & Eide), hydraulic uplift of the base, piping and boiling, toe stability, overall stability, vertical equilibrium of the wall.
- Groundwater: cut-off walls, dewatering (deep wells, wellpoints, ejectors), recharge, the effect of drawdown on nearby settlement.
- **Ground movements and damage:** wall deflection and settlement-profile envelopes (Peck 1969; Clough & O'Rourke 1990; Hsieh & Ou 1998); system stiffness (Clough et al. 1989); building damage assessment (Burland & Wroth; Boscardin & Cording; Mair, Taylor & Burland 1996).
- **Cut-and-cover:** construction sequence, temporary vs permanent works, base slab uplift (tension piles or anchors), waterproofing, decking, utility diversions, and wall-to-slab connections.
- Instrumentation and the **observational method**: inclinometers, prop load cells, piezometers, monitoring points, TAM trigger levels (green/amber/red).

**Numbers and equations**
- Ka = (1 − sin φ′)/(1 + sin φ′) = tan²(45 − φ′/2); Kp = 1/Ka (Rankine).
- Terzaghi–Peck apparent pressure (braced cuts): sand 0.65·Ka·γ·H (uniform); soft to medium clay uses the larger of γH(1 − 4su/γH) and 0.3γH when the stability number N = γH/su > 4.
- Basal heave FS ≈ Nc·su/(γH + q), with Nc from Bjerrum & Eide (5.14–9).
- Typical maximum wall deflection: about 0.2% of H for stiff clays, residual soils, and sands (Clough & O'Rourke average); 0.5–2% of H for soft clays with low system stiffness.
- Burland damage categories by limiting tensile strain: 0 Negligible < 0.05%; 1 Very slight 0.05–0.075%; 2 Slight 0.075–0.15%; 3 Moderate 0.15–0.3%; 4–5 Severe and very severe > 0.3%.

**Practice questions**
1. Walk through designing a 15 m deep propped diaphragm-wall excavation in soft clay over sand with a confined aquifer. What can fail, and how do you check each mechanism?
2. Top-down vs bottom-up cut-and-cover: what are the advantages, disadvantages, and effects on ground movement?
3. How do you set trigger levels for monitoring, and what happens at red?
4. Why is the "moderately conservative" parameter set used under the observational method (CIRIA C760 / C185)?

---

## 6. Tunnelling

**Refresh**
- Methods: open-face and shielded TBMs (**EPB vs slurry vs hard rock**: open gripper, single and double shield), SCL/NATM (sequential excavation, sprayed concrete), drill and blast, cut-and-cover, immersed tube, pipe jacking and microtunnelling, jacked box.
- Face stability: stability ratio N (Broms & Bennermark), face support pressure (Anagnostou & Kovári wedge model, DAUB recommendations), blow-outs.
- **Ground movements:** volume loss VL, the Gaussian transverse settlement trough, longitudinal profile, effects of twin tunnels and their interaction; building damage assessment (the three-stage approach: greenfield screening → second stage → detailed assessment); mitigation through compensation grouting, permeation grouting, or underpinning.
- Linings: precast segments (ring build, ring taper, gaskets, design load cases from handling through TBM thrust jacks to the ground), steel-fibre reinforced concrete segments, SCL primary and secondary linings, waterproofing (sheet vs sprayed membrane).
- Rock tunnels: ground reaction curve / **convergence–confinement method**, rock bolts, shotcrete, steel sets, squeezing and swelling ground, rockburst, wedge analysis (UnWedge), Q- and RMR-based support.
- Ground treatment: dewatering, grouting, ground freezing, spiling and forepoling, face bolts, umbrella arch.
- Risk: the Joint Code of Practice, risk registers, GBR, TBM selection.

**Numbers and equations**
- Transverse trough: Sv(y) = Smax·exp(−y²/2i²); i = K·z0, with K ≈ 0.5 in clays and 0.25–0.45 in sands (O'Reilly & New).
- Settlement trough volume: Vs = √(2π)·i·Smax; VL = Vs / (πD²/4).
- Typical VL: about 0.5–1.5% for closed-face TBMs in London Clay or sands (often < 1% with good EPB/slurry control); SCL 1–2%.
- Stability ratio N = (σv − σT)/su; N ≲ 5–6 is usually stable for undrained soil faces.
- Hoek & Marinos squeezing: strain ε ≈ 0.2·(σcm/p0)^−2 (%). More than about 1% means squeezing problems are possible.

**Practice questions**
1. EPB or slurry TBM for a mixed sand–gravel–clay alignment below the water table? Justify the choice.
2. Explain the convergence–confinement method and when support should be installed.
3. How would you assess and protect a masonry building above a new tunnel?
4. Name the load cases for a precast segment design.

---

## 7. Rock mechanics

**Refresh**
- Intact rock: UCS, tensile strength, Young's modulus, Poisson's ratio; anisotropy; weathering grades.
- Discontinuities: orientation, spacing, persistence, roughness (JRC), wall strength (JCS), aperture, infill; Barton–Bandis shear strength; stereonets and kinematic analysis (Markland test for planar, wedge, and toppling failure).
- Rock-mass classification: RQD, RMR (Bieniawski 1989), Q-system (Barton), **GSI**; generalised **Hoek–Brown** criterion; rock-mass modulus (Hoek & Diederichs 2006).
- In-situ stress: k = σh/σv, measurement (hydraulic fracturing, overcoring), Hoek–Brown k vs depth.
- Rock slopes and rockfall; rock foundations (socketed piles: Rowe & Armitage, Kulhawy); excavation-damaged zone; blasting vibration.

**Numbers and equations**
- RQD = Σ(core pieces ≥ 100 mm) / run length × 100%.
- Q = (RQD/Jn)·(Jr/Ja)·(Jw/SRF).
- Hoek–Brown: σ′1 = σ′3 + σci·(mb·σ′3/σci + s)^a, with mb, s, and a from GSI, mi, and the disturbance factor D.
- Approximate correlation: RMR ≈ 9 ln Q + 44 (Bieniawski).
- Point load: UCS ≈ (20–25)·Is(50).

**Practice questions**
1. How do you get rock-mass strength and stiffness for a tunnel model from borehole logs?
2. Explain the disturbance factor D and when you would use D > 0.
3. Run a kinematic check for a road cut slope from discontinuity data.

---

## 8. Codes and design philosophy

**Refresh**
- **Eurocode 7 (1st generation, still widely used):** limit states (EQU, STR, GEO, UPL, HYD); design approaches DA1 (combinations A1+M1+R1 and A2+M2+R1), DA2, DA3; characteristic values as "cautious estimates".
- **Eurocode 7 (2nd generation, EN 1997-1/-2:2024, -3:2025):** see §9.
- **US LRFD:** load and resistance factors, AASHTO Sections 10 and 11; ASD for buildings (IBC).
- Serviceability vs ultimate limit states; the observational method (EC7 §2.7 in the 1st generation).
- Seismic: site classes (Vs30), liquefaction triggering (Boulanger & Idriss 2014), lateral spreading, seismic earth pressures (Mononobe–Okabe), EN 1998-5.

**Practice questions**
1. Explain DA1 in Eurocode 7 and why Combination 2 often governs for pile length or wall embedment.
2. What is a characteristic value in Eurocode 7, and how does the 2nd generation change how you derive it?

---

## 9. Newer topics to study (what current interviews ask about)

These topics take you from "refreshed" to "up to date". Each lists a starting source.

1. **Second-generation Eurocode 7** (EN 1997-1/-2:2024, -3:2025, with EN 1990:2023). Key ideas:
   - the **Ground Model** and **Geotechnical Design Model**
   - **Geotechnical Category** (from Consequence Class plus Geotechnical Complexity Class)
   - the Geotechnical Design Report
   - representative vs derived values
   - verification by numerical methods and reliability-based design
   - new clauses for ground reinforcement and improvement (Part 3)
   *Sources:* the Stuttgart/DFI 2025 paper, the LNEC paper series, ISSMGE EC7 explainers, and the JRC technical reports (SOURCES §8).
2. **Small-strain stiffness and advanced constitutive models**. Learn the Hardening Soil and HS-small models (G0, γ0.7), Soft Soil Creep, NGI-ADP (anisotropic undrained), hypoplasticity, and how to calibrate them from SCPT and triaxial data. *Sources:* Burland (1989), the PLAXIS material models manual, and the Benz (2007) thesis.
3. **Digital geotechnics and BIM**. Covers ISO 19650, **IFC 4.3** (which includes alignment and geotechnical entities), AGS 4, 3D ground models in Leapfrog, digital twins of excavations, and the ITA WG22 BIM guideline. *Source:* ITA WG22.
4. **Machine learning and data analytics**. Examples: CPT-based soil classification with ML, TBM performance and parameter prediction, settlement back-analysis with Bayesian updating, anomaly detection in monitoring data. Know the limits: data leakage, extrapolation, explainability.
5. **Sensing and monitoring**. Covers distributed fibre-optic sensing (DFOS, BOTDR) in piles, walls, and segments; InSAR for settlement monitoring over large areas; automated total stations; IoT sensors; real-time TAM systems. *Sources:* Crossrail Learning Legacy and the BTS/ICE *Monitoring Underground Construction*.
6. **Embodied carbon in geotechnics**. Covers the carbon cost of foundations and retaining walls, low-carbon concrete (GGBS), **foundation reuse**, optimised pile design (settlement-based design, using load tests to reduce factors), and the EFFC–DFI carbon calculator.
7. **Reliability and risk-based design**. Covers probabilistic slope and foundation analysis, random fields, Bayesian back-analysis, and the observational method as a risk tool. *Source:* JRC report on reliability-based verification.
8. **Energy geostructures and the ground's role in climate**. Covers thermal (energy) piles and tunnel linings, thermo-mechanical effects on pile capacity, and climate resilience (changing groundwater levels, desiccation of clays, slope stability under extreme rainfall).
9. **Modern lining technology**. Covers steel-fibre reinforced segments (ITA WG2 2019 guidelines), permanent sprayed-concrete linings with sprayed waterproofing membranes (composite shell linings), and segment damage (spalling, cracking from jack eccentricity).
10. **Contracting and risk allocation**. Covers GBRs (ASCE MOP 154, 2022), NEC/FIDIC unforeseen ground conditions clauses, and design-build. This is often discussed in interviews for tunnel and excavation jobs.
11. **Liquefaction and seismic geotechnics updates**. Covers Boulanger & Idriss (2014) CPT/SPT triggering, performance-based design, and ground improvement against liquefaction (DSM grids, stone columns, drains).

---

## 10. Case histories to know (2-minute stories)

| Case | Lesson |
|---|---|
| Nicoll Highway collapse, Singapore (2004) | Deep excavation failure in soft marine clay: under-designed strut-waler connection, misuse of an undrained model (Method A in PLAXIS overestimated su), ignored monitoring |
| Heathrow Express NATM collapse (1994) | SCL quality control, joint defects, the role of monitoring interpretation |
| Cologne archive collapse (2009) | Leaky diaphragm-wall joint → hydraulic failure of the excavation base |
| Leaning Tower of Pisa stabilisation (Burland, 1990s–2001) | Soil extraction (under-excavation), consolidation, observational method |
| Crossrail / Elizabeth Line, London | Settlement prediction and compensation grouting; SCL station caverns; digital monitoring |
| Big Dig, Boston | Cut-and-cover in urban soft ground; slurry walls; leak problems |
| Transbay Transit Center, San Francisco | Deep excavation in soft Bay Mud next to high-rise buildings (and the nearby Millennium Tower settlement) |
| Marmaray / Eurasia Tunnel, Istanbul | Immersed tube and slurry TBM under the Bosphorus; seismic design in a high-seismicity zone |

---

*Edit this guide as you study. Add questions you were actually asked in interviews to the "Practice questions" lists.*
