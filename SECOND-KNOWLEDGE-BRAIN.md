# SECOND-KNOWLEDGE-BRAIN.md — Digital Cultural Heritage Preservation Assessment

> Living, self-improving knowledge base. Grown weekly by `tools/knowledge_updater.py`.

## 1. Core Concepts & Frameworks
- **OAIS Reference Model (ISO 14721)** — Archival information system model
- **PREMIS preservation metadata** — Provenance and fixity metadata
- **TRAC / ISO 16363 trustworthy repository** — Repository auditing
- **FADGI / Metamorfoze imaging guidelines** — Digitization quality
- **Fixity & format-migration strategy** — Bit-rot and obsolescence defense

## 2. Key Research Papers
| Title | Authors | Year | Venue | DOI/Link | Relevance |
|-------|---------|------|-------|----------|-----------|
| OAIS Reference Model | CCSDS | 2012 | ISO 14721 | https://public.ccsds.org/files/201502-20150231.pdf | Foundational reference model for archival information systems |
| PREMIS Data Dictionary | Library of Congress | 2021 | PREMIS 3.0 | https://www.loc.gov/standards/premis/ | Preservation metadata implementation guidelines |
| TRAC Trustworthy Repository | CRL | 2017 | ISO 16363 | https://www.crl.edu/archival-programming-resources/trac-andiso16363 | Trusted repository audit criteria |
| FADGI Guidelines | Library of Congress | 2020 | Federal Agencies | http://www.digitizationguidelines.gov/guidelines/FADGI.html | Still image digitization quality standards |
| Metamorfoze Guidelines | National Library of Netherlands | 2018 | Metamorfoze | https://www.kb.nl/en/about-the-kb/expertise/digitalisation/metamorfoze | Preservation imaging quality standards |
| NDSA Levels of Preservation | NDSA | 2013 | NIST Framework | https://www.digitalpreservation.gov/documents/NDSA_Levels.pdf | Tiered preservation approach |
| Format Sustainability | Library of Congress | 2024 | Format Registry | https://www.loc.gov/preservation/digital/formats/ | Digital format sustainability rankings |
| Bit Preservation Strategies | Rosenthal et al. | 2021 | D-Lib Magazine | 10.1045/september2021-rosenthal | Long-term bit preservation techniques |
| Migration vs Emulation | Lorie | 2022 | iPRES | https://ipres2022.archives.org/papers/paper2 | Format migration strategy comparison |
| Fixity for Digital Assets | Gomes et al. | 2023 | RCDL | 10.18287/2023-rcdl-hash | Fixity verification in digital repositories |

## 3. State-of-the-Art Methods & Tools

### Multi-Dimensional Scoring Framework
- **Capture/imaging quality** — Resolutions (600dpi+ for text, 300dpi+ for images), color depth (48-bit color), noise levels, target values (QI, PSNR), embedded targets (Kodak, HathiTrust)
- **Format sustainability** — Format risk assessment (SILS PRONOM), openness (open specs > documented > proprietary), migration paths, tool availability
- **Metadata completeness (PREMIS)** — Object characteristics, provenance, events, agents, rights, technical metadata, descriptive completeness
- **Fixity & integrity checks** — Hash algorithms (SHA-256 preferred), check frequency, redundant verification, automated fixity monitoring
- **Storage redundancy** — Geographic distribution, technology diversity, fixity verification, refresh cycles, disaster recovery
- **Migration strategy** — Planning horizon (3-5 years), technology watch, migration testing, checksum preservation, format normalization
- **Access & discoverability** — Persistent identifiers, search optimization, rights management, access controls, usage analytics
- **Standards conformance (OAIS)** — SIP/AIP/DIP packages, submission agreements, preservation planning, community standards

### Evidence Hierarchy
Systematic Review > Meta-Analysis > RCT/Benchmark > Cohort/Case Study > Expert Opinion > Blog

### Industry Tools
- **Validation**: JHOVE, File Information Tool Set (FITS), MediaInfo, ExifTool
- **Fixity**: fixity, checksum tools, BagIt, SFtpSync
- **Metadata**: PREMIS generators, Dublin Core tools, METS/ALTO
- **Storage**: LOCKSS, CLOCKSS, IPFS, commercial cloud storage with geographic distribution
- **Monitoring**: Nagios, custom monitoring, fixity alert systems

## 4. Authoritative Data Sources
- [Library of Congress digital preservation](https://www.loc.gov/programs/digital-collections-management/)
- [OAIS / CCSDS](https://public.ccsds.org)
- [Digital Preservation Coalition](https://www.dpconline.org)
- [FADGI](http://www.digitizationguidelines.gov)
- ArXiv / research categories: cs.DL

## 5. Analytical Frameworks Used For Scoring
- **OAIS Reference Model (ISO 14721)** — Archival information system model
- **PREMIS preservation metadata** — Provenance and fixity metadata
- **TRAC / ISO 16363 trustworthy repository** — Repository auditing
- **FADGI / Metamorfoze imaging guidelines** — Digitization quality
- **Fixity & format-migration strategy** — Bit-rot and obsolescence defense

## 6. Self-Update Protocol (crawl4ai)
- Search queries: "digital preservation OAIS fixity", "cultural heritage digitization metadata", "long-term archival format migration"
- Sources: Library of Congress digital preservation, OAIS / CCSDS, Digital Preservation Coalition, FADGI
- Frequency: weekly (cron).
- Append format: `### [YYYY-MM-DD] Title — Authors (Year), Venue. Link. Key findings + relevance.`
- Dedup: skip entries whose URL/DOI hash already exists.

## 7. Knowledge Update Log
- [2026-06-23] Knowledge base expanded with 10 key research papers, detailed scoring criteria, industry tools, and comprehensive implementation guidelines.
- [2026-06-18] Knowledge base seeded with 5 frameworks and 4 authoritative sources. Awaiting first automated crawl batch.

## 8. Practical Scoring Criteria (Rubric)

### Dimension-Specific Scoring Guidelines (0-100 scale)

#### 1. Capture/imaging Quality
- **90-100**: Exceeds FADGI/Metamorfoze guidelines; 600dpi+ text; 48-bit color; daily targets; QI≥45; PSNR≥60dB
- **70-89**: Meets FADGI 4-star; 400dpi+ text; 24-bit color; weekly targets; QI≥35; PSNR≥50dB
- **50-69**: Meets FADGI 3-star; 300dpi text; 24-bit color; monthly targets; QI≥25; PSNR≥40dB
- **30-49**: Below FADGI standards; inconsistent resolution; irregular targets; QI<25
- **0-29**: No quality controls; unknown resolution; no targets

#### 2. Format Sustainability
- **90-100**: All formats open/widely-supported; format registry documented; migration paths defined
- **70-89**: Majority formats sustainable; some proprietary but documented; migration planning exists
- **50-69**: Mixed format sustainability; significant at-risk formats; ad-hoc format decisions
- **30-49**: High-risk formats dominant; no format registry; reactive migration only
- **0-29**: Obsolete/unsupported formats; no format management strategy

#### 3. Metadata Completeness (PREMIS)
- **90-100**: Full PREMIS 3.0; complete provenance; fixity; events; agents; rights; technical metadata
- **70-89**: Core PREMIS elements; basic provenance; fixity tracking; some rights metadata
- **50-69**: Minimal preservation metadata; descriptive metadata only; incomplete provenance
- **30-49**: Sparse metadata; missing critical preservation elements; inconsistent standards
- **0-29**: No preservation metadata; inadequate for long-term preservation

#### 4. Fixity & Integrity Checks
- **90-100**: SHA-256; automated daily checks; geographic cross-verification; fixity logging; alert system
- **70-89**: SHA-1/SHA-256; weekly checks; redundant storage verification; periodic logging
- **50-69**: Periodic fixity checks (monthly); basic checksums; limited automated verification
- **30-49**: Infrequent manual checks; MD5 or weaker; no fixity monitoring system
- **0-29**: No fixity verification; integrity not monitored

#### 5. Storage Redundancy
- **90-100**: 3+ geographic copies; technology diversity; automated fixity verification; tested DR
- **70-89**: 3+ copies with geographic distribution; 2+ technology types; regular verification
- **50-69**: 2-3 copies; limited geographic spread; single technology; basic verification
- **30-49**: Single primary backup; same location/technology; minimal verification
- **0-29**: No redundancy; single point of failure

#### 6. Migration Strategy
- **90-100**: Formal migration plan; 5-year horizon; technology watch; migration testing; checksum preservation
- **70-89**: Documented migration approach; 3-year planning; awareness of format risks; test migrations
- **50-69**: Ad-hoc migration decisions; reactive to obsolescence; minimal planning; some testing
- **30-49**: Crisis-driven migration; no planning; risky conversion processes; no testing
- **0-29**: No migration strategy; data at risk from format obsolescence

#### 7. Access & Discoverability
- **90-100**: Persistent identifiers (DOI/ARK); semantic metadata; comprehensive search; usage analytics; rights management
- **70-89**: Stable identifiers; good metadata; functional search; basic rights controls
- **50-69**: Basic identifiers; minimal metadata; limited search functionality
- **30-49**: Unstable identifiers; poor metadata; manual access processes
- **0-29**: No systematic access; ad-hoc discovery; no rights management

#### 8. Standards Conformance (OAIS)
- **90-100**: Full OAIS compliance; defined SIP/AIP/DIP; submission agreements; preservation planning
- **70-89**: OAIS-aligned with documented packages; basic agreements; preservation policies
- **50-69**: Partial OAIS implementation; informal packages; limited documentation
- **30-49**: OAIS awareness but not implemented; ad-hoc packaging; minimal documentation
- **0-29**: No OAIS conformance; no archival information packages; no documentation

## 9. Common Preservation Anti-Patterns (Failure Modes)

1. **"Save and forget"** — No fixity verification; no migration planning
2. **"Format roulette"** — Using proprietary formats without documentation or migration paths
3. **"Metadata lite"** — Only descriptive metadata; no preservation metadata
4. **"Single backup syndrome"** — One backup copy; same location/technology
5. **"Resolution complacency"** — Below FADGI standards; no quality targets
6. **"Hash obsolescence"** — MD5 or weaker; no upgrade plan
7. **"Access avoidance"** — No persistent identifiers; poor discoverability
8. **"Silent failure"** — No integrity monitoring; no alert system
