# TS-Com Project Documentation Suite

**Animal-Ai Network \- Undergraduate Computer Networks Course** *CP352005 Networks \- 4-Week Sprint with 5-Member Role-Assigned Team*  
รายวิชา: CP352005 Networks  
**กลุ่ม:** 14  
**รายชื่อสมาชิก:**

673380036-3 		ณภัทร อรัญพูล   
673380043-6 		ธนินธร อันทรบุตร   
673380061-4 		ศุภกร กรมรินทร์   
673380267-4 		ณัชพล เพ็งพล   
673380268-2 		ณัฐกรณ์ อินธิสาร 

---

# File 1: architecture\_spec.md

`# Animal-AI Network Architecture Specification v1.0`  
`**Architectural Review Document - CP352005 Networks**`  
\*Lead Architect: ณภัทร อรัญพล (673380036-3)\*

`## Document Control`

`| Version | Date | Author | Role | Changes |`  
`|---------|------|--------|------|---------|`  
| v1.0 | \[Date\] | ณภัทร อรัญพล | Architect | Initial architectural specification |

`## Part 1: Executive Summary`

`### 1.1 Project Vision`  
`Animal-AI Network is a conceptual network architecture that enables communication between animals, AI systems, and humans by integrating biological signals, behavioral data, and semantic understanding directly into the network fabric. This project demonstrates understanding of layered network design, routing protocols, addressing schemes, and AI integration within the constraints of an undergraduate course.`

`### 1.2 Educational Objectives`  
`- Understand limitations of traditional TCP/IP architecture for biological data`  
`- Design novel network layers for cross-species communication`  
`- Integrate AI into network infrastructure at multiple layers`  
`- Apply networking concepts to real-world conservation and welfare applications`  
`- Practice technical documentation and team collaboration`

`### 1.3 Scope and Constraints`

`| Aspect | In Scope | Out of Scope |`  
`|--------|----------|--------------|`  
`| Architecture | Layered design, protocols, addressing | Physical hardware implementation |`  
`| Simulation | Python-based network simulation | Real animal testing |`  
`| AI Integration | Rule-based AI, intent classification | Complex machine learning models |`  
`| Protocols | Bio-Addressing, Semantic Routing | Production-ready protocols |`  
`| Testing | Unit tests, integration tests | Real-world deployment |`  
`| Use Cases | Wildlife, Livestock, Pet applications | All animal species |`

`## Part 2: Architectural Review`

`### 2.1 Architecture Overview`

┌─────────────────────────────────────────────────────────────┐  
│ Layer 5: Semantic Application Layer │  
│ (Wildlife Monitor, Livestock Manager, Pet Translator) │  
├─────────────────────────────────────────────────────────────┤  
│ Layer 4: Context-Aware Transport Layer │  
│ (Priority Management, Adaptive Reliability) │  
├─────────────────────────────────────────────────────────────┤  
│ Layer 3: AI-Native Network Layer │  
│ (Bio-Addressing, Semantic Routing Protocol) │  
├─────────────────────────────────────────────────────────────┤  
│ Layer 2: Bio-Signal Link Layer │  
│ (Bio-Frame Format, Signal Synchronization) │  
├─────────────────────────────────────────────────────────────┤  
│ Layer 1: Biological Physical Layer │  
│ (Sensors, Wearables, Bio-signal Acquisition) │  
└─────────────────────────────────────────────────────────────┘  
`↑`  
AI Integration  
(Embedded at Every Layer)

`### 2.2 Layer-by-Layer Architecture Review`

`#### 2.2.1 Physical Layer (Biological Signal Acquisition)`  
\*\*Design Review Status: ✅ Approved with Notes\*\*

`| Aspect | Assessment | Notes |`  
`|--------|------------|-------|`  
`| Completeness | High | Well-defined sensor interfaces |`  
`| Feasibility | High | Python simulation achievable |`  
`| Integration | Medium | Clear interfaces to Data Link |`  
`| Innovation | Medium | Novel bio-signal framing |`

`**Interface Definition:**`  
```` ```python ````  
`class BiologicalPhysicalLayer:`  
    `def __init__(self):`  
        `self.sensors = {}  # Dictionary of active sensors`  
          
    `def register_sensor(self, sensor_id, sensor_type, species):`  
        `"""Register a biological sensor for an animal"""`  
          
    `def acquire_signal(self, animal_id, signal_type):`  
        `"""Capture raw biological signal from animal"""`  
        `# Returns: raw_signal_data, timestamp, confidence`  
          
    `def get_sensor_status(self, animal_id):`  
        `"""Check if animal's sensors are operational"""`

**Risks:**

- Over-complexity in link simulation  
- Performance issues with large simulations

#### 2.2.2 Data Link Layer \- Chrono-Anchor Addressing Protocol (CAAP)

**Design Review Status: ✅ Approved**  
**Address Resolution:**

`class BSLP:`  
    `def __init__(self):`  
        `self.frame_buffer = []`  
          
    `def create_frame(self, animal_id, signal_type, data, context):`  
        `"""Pack biological data into frame format"""`  
          
    `def parse_frame(self, raw_frame):`  
        `"""Extract data from received frame"""`  
          
    `def validate_frame(self, frame):`  
        `"""Check frame integrity via checksum"""`  
          
    `def get_animal_from_frame(self, frame):`  
        `"""Extract animal identification"""`

**Review Notes:**

- Address format supports all required dimensions  
- Resolution mechanism clearly defined  
- Interface to Network layer well-specified

#### 2.2.3 Network Layer \- Bio-Addressing & Semantic Routing Protocol (SRP)

**Design Review Status: ⚠️ Conditional Approval**

**Semantic Routing Algorithm:**

`class SemanticRoutingProtocol:`  
    `def __init__(self):`  
        `self.routing_table = {}`  
        `self.priority_levels = {`  
            `"CRITICAL": 0,    # Life-threatening`  
            `"HIGH": 1,         # Health emergency`  
            `"MEDIUM": 2,       # Behavioral change`  
            `"LOW": 3,          # Routine monitoring`  
            `"BACKGROUND": 4    # Research data`  
        `}`  
          
    `def calculate_route(self, source_address, dest_address, priority):`  
        `"""`  
        `Route based on semantic meaning and priority`  
          
        `Cost = α*priority_weight + β*species_similarity + γ*network_distance`  
        `where:`  
        `- priority_weight = priority level (0-4)`  
        `- species_similarity = taxonomic distance`  
        `- network_distance = physical/network hops`  
        `- α, β, γ = weighting factors`  
        `"""`  
          
    `def determine_priority(self, signal_type, context_flags):`  
        `"""Calculate priority from signal and context"""`  
        `if "distress" in context_flags:`  
            `return self.priority_levels["CRITICAL"]`  
        `elif signal_type in ["biometric_abnormal", "injury_detected"]:`  
            `return self.priority_levels["HIGH"]`  
        `# ... etc.`  
          
    `def forward_packet(self, packet):`  
        `"""Determine next hop based on routing decision"""`

**Conditional Approval Notes:**

- Need to specify weighting factors (α,β,γ)  
- Require routing table refresh interval  
- Missing convergence analysis

**Required Changes:**

* Define default weighting factors (α=0.5, β=0.3, γ=0.2)  
* Specify routing update interval (60s simulation time)  
* Add route caching mechanism  
* Document routing table structure

#### 2.2.4 Transport Layer \- Context-Aware Transport Protocol (CATP)

**Design Review Status: ✅ Approved**

**Paradox Detection Rules:** | Rule ID | Description | Action | |---------|-------------|--------| | R001 | Grandfather Paradox | Block packet | | R002 | Information Loop | Block after 10 hops | | R003 | Causality Violation | Log and warn | | R004 | Temporal Consistency | Allow |

**Priority Management:**

`class ContextAwareTransport:`  
    `def __init__(self):`  
        `self.active_sessions = {}`  
        `self.priority_queues = {0: [], 1: [], 2: [], 3: [], 4: []}`  
          
    `def send_data(self, packet, priority):`  
        `"""Queue data based on priority"""`  
        `self.priority_queues[priority].append(packet)`  
          
    `def receive_data(self, session_id):`  
        `"""Retrieve data for session"""`  
          
    `def adaptive_reliability(self, signal_type, priority):`  
        `"""`  
        `Different reliability for different signals:`  
        `- CRITICAL: 100% reliable (ack + retransmission)`  
        `- HIGH: 95% reliable (ack only)`  
        `- MEDIUM: Best effort with checksum`  
        `- LOW: Best effort only`  
        `"""`  
          
    `def flow_control(self, animal_activity_state):`  
        `"""`  
        `Adjust data rate based on animal activity:`  
        `- Active: High data rate`  
        `- Resting: Medium data rate`  
        `- Sleeping: Low data rate (power saving)`  
        `"""`

**Review Notes:**

- Rule-based approach appropriate for simulation  
- Human review requirement good for edge cases  
- Consider adding paradox probability scoring

#### 2.2.5 Session Layer \- Animal Session Protocol (ASP)

**Design Review Status: ✅ Approved**

**Session Management:**

`class AnimalSession:`  
    `def __init__(self, session_id, animal_id, app_type):`  
        `self.session_id = session_id`  
        `self.animal_id = animal_id`  
        `self.app_type = app_type  # wildlife/livestock/pet`  
        `self.state = "ESTABLISHING"`  
        `self.start_time = time.time()`  
        `self.data_buffer = []`  
          
    `def establish_session(self):`  
        `"""Initialize communication with animal"""`  
          
    `def maintain_session(self):`  
        `"""Keep session alive with heartbeat"""`  
          
    `def buffer_data(self, data):`  
        `"""Store data for this session"""`  
          
    `def close_session(self):`  
        `"""Terminate session gracefully"""`

#### 2.2.6 Presentation Layer \- Temporal AR Interface

**Design Review Status: ✅ Approved**

**Data Serialization:**

`class TemporalSerializer:`  
    `def encode_temporal_data(self, data, source_time):`  
        `"""Prepare data for temporal transmission"""`  
          
    `def decode_temporal_data(self, encoded_data, target_time):`  
        `"""Reconstruct data for target timeline"""`  
          
    `def handle_temporal_drift(self, data, time_delta):`  
        `"""Adjust for time-based data degradation"""`

#### 2.2.7 Application Layer \- Demo Applications

**Design Review Status: ✅ Approved**

**Application Suite:**

1.Wildlife Conservation Dashboard

2.Smart Livestock Manager

3.Pet Translator App

### **2.3 AI Integration Architecture**

AI Components by Layer:

| Layer | AI Component | Function |
| :---- | :---- | :---- |
| Layer 1 | Signal Processing AI | Noise reduction, signal enhancement |
| Layer 2 | Pattern Recognition AI | Activity classification, anomaly detection |
| Layer 3 | Semantic Routing AI | Context-aware routing decisions |
| Layer 4 | Priority Management AI | Data importance assessment |
| Layer 5 | Translation AI | Animal-to-human intent mapping |

### **2.4 Non-Functional Requirements Review**

| Requirement | Target | Current Status | Assessment |
| :---- | :---- | :---- | :---- |
| Scalability | Support 50+ animals | 10 nodes | ⚠️ Needs work |
| Performance | \<1s routing decision | \<0.5s | ✅ Good |
| Reliability | 95% packet delivery | Simulated | ⚠️ Needs test |
| Maintainability | Modular layers | Good | ✅ Good |
| Testability | Unit test coverage \>80% | Planned | ⚠️ In progress |

### 2.5 Security Architecture 

**Security Zones:**

┌─────────────────────────────────────┐  
│ Zone 1: Animal Domain                │  
│ (Sensors, Wearables)                 │  
│ Security: Physical \+ Basic Auth      │  
└─────────────────┬───────────────────┘  
                  │ Encrypted  
┌─────────────────▼───────────────────┐  
│ Zone 2: Edge Processing               │  
│ (Local Gateway, AI Preprocessing)     │  
│ Security: TLS \+ Authentication        │  
└─────────────────┬───────────────────┘  
                  │ Encrypted  
┌─────────────────▼───────────────────┐  
│ Zone 3: Core Network                  │  
│ (Routing, AI Processing)              │  
│ Security: IPSec \+ Access Control      │  
└─────────────────┬───────────────────┘  
                  │ Encrypted  
┌─────────────────▼───────────────────┐  
│ Zone 4: Application Layer             │  
│ (Dashboards, Alerts)                  │  
│ Security: HTTPS \+ User Auth           │  
└─────────────────────────────────────┘

---

## Part 3: Architecture Decisions Log

### Decision 1: Python-Based Simulation

**Date**: \[Date\]  
**Decision**: Use Python with NetworkX for simulation  
**Rationale**: Fast development, good visualization, team familiarity  
**Alternatives Considered**: NS-3, OMNeT++ (too complex for timeframe)  
**Status**: ✅ Approved

### Decision 2: Bio-Addressing Scheme

**Date**: \[Date\]  
**Decision**: Use hierarchical biological taxonomy (16-byte address)  
**Rationale**: Extensible, follows biological classification, includes individual ID  
**Alternatives Considered**: Flat addressing (insufficient), MAC-like (no species info)  
**Status**: ✅ Approved

### **Decision 3: Audit Logging**

**Date**: \[Date\]  
**Decision**: Comprehensive audit logging for all critical events  
**Rationale**: Required for security analysis and compliance  
**Alternatives Considered**: Minimal logging (insufficient for security)  
**Status**: ✅ Approved

---

## Part 4: Architectural Review Sign-off

| Role | Name | Signature | Date | Comments |
| :---- | :---- | :---- | :---- | :---- |
| Architect | ศุภกร กรมรินทร์ |  |  |  |
| Engineer | ณภัทร อรัญพูล |  |  |  |
| Specialist | ณัฐกรณ์ อินธิสาร |  |  |  |
| DevOps | ณัชพล เพ็งพล |  |  |  |
| Tester/QA | ธนินธร อันทรบุตร |  |  |  |

**Review Outcome:** ⚠️ Conditional Approval  
**Conditions to be met by:** Week 2, Day 3  
**Conditions:**

1. Specify TRP weighting factors  
2. Define routing update intervals  
3. Add paradox probability scoring

---

## Appendices

### Appendix A: Glossary

| Term | Definition |
| :---- | :---- |
| Bio-Address | Hierarchical address based on biological taxonomy |
| Semantic Routing | Routing based on meaning and context |
| Bio-Frame | Data frame format for biological signals |
| Intent | Underlying meaning of animal communication |
| Cross-Species | Communication between different species |
| Context-Aware | System considering environmental factors |

### Appendix B: References

1. Kurose & Ross, "Computer Networking: A Top-Down Approach"  
2. Tanenbaum, "Computer Networks"  
3. Novikov Self-Consistency Principle  
4. OSI Model \- ISO/IEC 7498-1

---

*This architectural specification is approved for the CP352005 Networks undergraduate project.*

`---`

`## File 2: implementation_plan.md`

```` ```markdown ````  
`# Animal-AI Network Implementation Plan v1.0`  
`**4-Week Sprint Planning - CP352005 Networks**`  
\*Lead DevOps: ณัชพล เพ็งพล (673380267-4)\*

`## Document Control`

`| Version | Date | Author | Role | Changes |`  
`|---------|------|--------|------|---------|`  
| v1.0 | \[Date\] | ณัชพล เพ็งพล | DevOps | Initial implementation analysis |

`## Part 1: Implementation Overview`

`### 1.1 Technical Stack`

`| Component | Technology | Justification |`  
`|-----------|------------|---------------|`  
`| Language | Python 3.8+ | Team familiarity, rapid development |`  
`| Simulation | NetworkX | Graph-based network simulation |`  
`| Visualization | Matplotlib, Plotly | Clear network diagrams |`  
`| Testing | PyTest | Comprehensive test framework |`  
`| Version Control | Git/GitHub | Industry standard |`  
`| Documentation | Markdown, MkDocs | Easy to maintain |`  
`| Security | Cryptography library | AES-256 encryption |`  
`| Logging | Python logging module | Audit trail |`

`### 1.2 Dependency Analysis`

`Week 1          Week 2          Week 3          Week 4`  
`Foundation      Implementation  Integration     Delivery`  
─────────────────────────────────────────────────────────────────►

┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐  
│ Architecture│   │ Protocols   │   │ Integration │   │ Final Demo  │  
│ Design      │──▶│ Implementation│──▶│ & Testing  │──▶│ & Delivery  │  
└─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘  
       │                  │                  │                  │  
       ▼                  ▼                  ▼                  ▼  
┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐  
│• BSLP Spec  │   │• BSLP Code  │   │• BSLP Test  │   │• BSLP       │  
│• SRP Spec   │   │• SRP Code   │   │• SRP Test   │   │  Integrated │  
│• CATP Spec  │──▶│• CATP Code  │──▶│• CATP Test  │──▶│• Network    │  
│• ASP Spec   │   │• ASP Code   │   │• ASP Test   │   │  Layer Ready│  
│• AIS Spec   │   │• AIS Code   │   │• AIS Test   │   │• Transport  │  
│• App Design │   │• App Code   │   │• App Test   │   │  Layer Ready│  
│• Sim Setup  │   │• Sim Dev    │   │• Sim Test   │   │• Full System│  
└─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘

`**Critical Path:** TRP Implementation → Integration → Testing`    
`**Parallelizable Tasks:** CAAP, PPP, Visualization, Documentation`

`### 1.3 Technical Debt Assessment`  
`Potential Debt	Impact	Mitigation Strategy`  
Routing algorithm too complex	High	เริ่มจาก simple ก่อน แล้วค่อยเพิ่มความซับซ้อนทีหลัง  
Simulation performance	Medium	ทดสอบ performance ตั้งแต่เนิ่น ๆ, optimize ทีหลัง  
Integration friction	High	รวมโค้ดทุกวัน, กำหนด interface ให้ชัดเจน  
Documentation gaps	Medium	เขียน docs ไปพร้อมกับเขียนโค้ด  
AI complexity	High	ใช้ rule-based แทน Machine Learning  
Scope creep	Medium	ยึดตาม MVP 3 use cases เท่านั้น  
`Team coordination	Medium	Daily standup, clear role assignments`  
`Testing coverage	Medium	Write tests alongside code (TDD approach)`

`---`

`## Part 2: 4-Week Sprint Planning`  
`Week 1: Foundation Sprint (Days 1-5)`  
`Theme: Architecture, Setup, and Component Design`

`Day 1: Kickoff & Environment Setup`  
`Time	Activity	Lead	Participants`  
`9:00-10:00	Sprint Planning	DevOps	All`  
`10:00-12:00	Environment Setup	DevOps	All`  
`13:00-15:00	Architecture Review	Architect	All`  
`15:00-17:00	Role-specific tasks	Each	Individual`  
`Deliverables:`

`GitHub repository created (DevOps)`

`Development environment documented (DevOps)`

`Requirements installed (All)`

`Initial architecture diagram (Architect)`

`Role Tasks:`

`Role	Tasks`  
`Architect	Finalize layer interfaces, create interface contracts`  
`Engineer	Review Python/NetworkX documentation, prototype simple graph`  
`Specialist	Research paradox rules, draft 5 core rules`  
`DevOps	Setup CI (GitHub Actions), create project board`  
`Tester/QA	Create test plan template, define test categories`  
`Day 2: Addressing & Physical Layer Design`  
`Focus: CAAP specification and link simulation`

`Pair Programming:`

`Architect + Engineer: Address format design`

`Specialist + Tester: Paradox rule documentation`

`Deliverables:`

`CAAP address format specification (Architect)`

`Address resolution algorithm (Engineer)`

`Link simulation prototype (Engineer)`

`Paradox rule v0.1 (Specialist)`

`Test cases for addressing (Tester)`

`Day 3: Routing Protocol Design`  
`Focus: TRP algorithm design`

`Deliverables:`

`TRP routing algorithm pseudo-code (Engineer)`

`Cost function definition (Architect + Specialist)`

`Routing table structure (Engineer)`

`Test cases for routing (Tester)`

`Key Decision: Finalize weighting factors (α,β,γ) for routing cost`

`Day 4: Paradox Prevention Design`  
`Focus: PPP rule engine`

`Deliverables:`

`Complete paradox rule set (Specialist)`

`Rule engine design (Engineer)`

`Validation interface (Architect)`

`Test cases for paradox scenarios (Tester)`

`Day 5: Week 1 Review & Integration`  
`Activities:`

`14:00-15:00: Code review session`

`15:00-16:00: Integration testing`

`16:00-17:00: Sprint review & Week 2 planning`

`Week 1 Success Criteria:`

`All specifications documented`

`Development environment working for all`

`Basic simulation framework created`

`Test framework established`

`CI passing on main branch`

`Week 2: Implementation Sprint (Days 6-10)`  
`Theme: Core Protocol Implementation`

`Day 6-7: CAAP & Physical Layer Implementation`  
`Lead: Engineer`  
`Support: Architect (code review), Tester (test cases)`

`Tasks:`

`Implement ChronoAnchorAddress class`

`Create address resolution module`

`Build link simulation with temporal metrics`

`Write unit tests (minimum 80% coverage)`

`Definition of Done:`

`Address creation and validation working`

`Resolution returns correct addresses`

`Link simulation calculates Δt correctly`

`All tests passing`

`Day 8-9: TRP Implementation`  
`Lead: Engineer`  
`Support: Specialist (routing metrics), Tester (test scenarios)`

`Tasks:`

`Implement routing table management`

`Code modified Dijkstra with temporal weights`

`Create route calculation module`

`Add route caching mechanism`

`Critical Path Item: Must be completed by Day 9 EOD`

`Day 10: PPP Implementation`  
`Lead: Specialist + Engineer`  
`Support: Tester (validation)`

`Tasks:`

`Implement paradox rule engine`

`Create packet validation pipeline`

`Add violation logging`

`Test with paradox scenarios`

`Week 2 Success Criteria:`

`All core protocols implemented`

`Unit tests passing (>80% coverage)`

`Individual components run independently`

`Documentation updated`

`Week 3: Integration Sprint (Days 11-15)`  
`Theme: Integration, Testing, and Refinement`

`Day 11: Component Integration - Phase 1`  
`Integration Order:`

`CAAP + Physical Layer`

`Add TRP`

`Add PPP`

`Integration Lead: DevOps`  
`Testing Lead: Tester`

`Activities:`

`Morning: Integrate CAAP + Physical`

`Afternoon: Add TRP, test routing`

`Evening: Run integration tests`

`Day 12: Component Integration - Phase 2`  
`Integration Tasks:`

`Add PPP to stack`

`Implement end-to-end packet flow`

`Create test harness`

`Milestone: First end-to-end packet transmission by EOD`

`Day 13: System Testing & Bug Fixes`  
`Testing Activities:`

`Test Suite	Owner	Target`  
`Unit Tests	Engineer	Re-run all`  
`Integration Tests	Tester	20 scenarios`  
`Performance Tests	DevOps	Response time <1s`  
`Paradox Scenarios	Specialist	10 edge cases`  
`Day 14: Visualization & Demo Development`  
`Lead: Engineer`  
`Support: All`

`Visualization Requirements:`

`Network topology graph (x vs t)`

`Packet flow animation`

`Routing decision display`

`Paradox detection alerts`

`Day 15: Week 3 Review & Dry Run`  
`Activities:`

`10:00-12:00: Full system test`

`13:00-15:00: Bug fixing`

`15:00-17:00: Internal demo dry run`

`Week 3 Success Criteria:`

`All components integrated`

`End-to-end packet flow working`

`3 demo scenarios functional`

`Visualization displays correctly`

`Test coverage >80%`

`Week 4: Delivery Sprint (Days 16-20)`  
`Theme: Finalization, Documentation, and Presentation`

`Day 16: Documentation Sprint`  
`Document	Owner	Template`  
`User Guide	DevOps	docs/user_guide.md`  
`API Reference	Engineer	docs/api.md`  
`Test Report	Tester	docs/test_report.md`  
`Architecture Final	Architect	architecture_spec.md`  
`Implementation Summary	All	README.md`  
`Day 17: Polish & Optimization`  
`Focus Areas:`

`Code cleanup and comments`

`Performance optimization`

`Edge case handling`

`Visualization enhancement`

`Day 18: Presentation Development`  
`Tasks:`

`Create slide deck (All)`

`Record demo video (Engineer)`

`Prepare live demo script (Tester)`

`Rehearse presentation (All)`

`Presentation Structure:`

`Section	Duration	Presenter`  
`Introduction	2 min	Architect`  
`Architecture	3 min	Architect`  
`Implementation	4 min	Engineer`  
`Paradox Prevention	3 min	Specialist`  
`Demo	5 min	Engineer`  
`Testing Results	2 min	Tester`  
`Conclusion	1 min	DevOps`  
`Day 19: Final Review & Rehearsal`  
`Schedule:`

`9:00-11:00: Final code review`

`11:00-12:00: Documentation review`

`13:00-15:00: Presentation rehearsal`

`15:00-16:00: Feedback & fixes`

`16:00-17:00: Final adjustments`

`Day 20: Submission Day`  
`Final Checklist:`

`Code:`

`All code pushed to main branch`

`Tagged as 'v1.0.0'`

`README updated with setup instructions`

`Requirements.txt complete`

`Documentation:`

`Architecture specification`

`Implementation plan`

`User guide`

`API documentation`

`Test report`

`**Presentation:**`  
`- [ ] Slide deck (PDF)`  
`- [ ] Demo video (MP4)`  
`- [ ] Live demo ready`

`**Submission Package:**`  
`- [ ] GitHub repository link`  
`- [ ] All deliverables zipped`  
`- [ ] Team contribution statement`  
`- [ ] Peer evaluations`

`---`

`## Part 3: Role-Specific Implementation Analysis`

`### 3.1 Architect's Implementation Analysis`

`**Key Concerns:**`  
`- Interface stability between layers during parallel development`  
`- Protocol compatibility across all network layers`  
`- Scalability of 4D addressing scheme for 10+ nodes`  
`- Maintaining architectural integrity through iterations`

`**Implementation Checklist:**`  
`[ ] Finalize all layer interface contracts`	  
`[ ] Validate address format with test cases`	  
`[ ] Document protocol message formats`	  
`[ ] Create architecture decision log (ADL)`	  
`[ ] Review all code against architecture spec`	  
`[ ] Track architectural drift weekly`

`**Risk Mitigation:**`  
`- Create interface mocks for parallel development by Week 1 Day 4`  
`- Schedule bi-weekly architecture review meetings (Wednesdays 15:00)`  
`- Maintain version control of all interface specifications`  
`- Document all architectural decisions with rationale`

`### 3.2 Engineer's Implementation Analysis`

`**Core Implementation Tasks:**`  
Priority 1 (Must Have \- Week 2\)  
Task					Estimated Hours	Dependencies		Status  
\[ \] ChronoAnchorAddress   
class implementation				4		Address spec		Planned  
\[ \] RoutingTable management system	6		None			Planned  
\[ \] Dijkstra with temporal weights		8		Routing spec		Planned  
\[ \] Packet structure definition			3		None			Planned  
\[ \] Basic simulation framework		10		All above		Planned

Priority 2 (Should Have \- Week 3\)  
Task					Estimated Hours	Dependencies		Status  
\[ \] Route caching mechanism		4			RoutingTable		Planned  
\[ \] Multi-path routing support		6			Dijkstra   
implementation	Planned  
\[ \] Basic visualization (NetworkX)	5			Simulation framework	Planned  
\[ \] Performance optimization		4			Working system	Planned

Priority 3 (Nice to Have \- Week 4\)  
Task					Estimated Hours	Dependencies		Status  
\[ \] Load balancing across   
temporal paths			6			Multi-path routing	Planned  
\[ \] Advanced routing metrics		4			Working TRP		Planned  
\[ \] GUI interface prototype		8			Visualization		Planned  
\[ \] Real-time topology updates	5			Simulation		Planned

`**Technical Challenges:**`  
`- Efficient routing in temporal dimension`  
`- Simulation performance with 10+ nodes`  
`- Integration with visualization`

`### 3.3 Specialist's Implementation Analysis`

`**Domain Rules Implementation:**`

`Rule Name|Complexity | Validation Method`  
`------------------------------------`  
`Grandfather Paradox | Medium | Unit tests with 5 scenarios`  
`Information Loop | Low | Simple counter test`  
`Causality Violation | High | 10 edge cases`  
`Temporal Consistency | Medium | Scenario testing`  
`Bootstrap Paradox | Medium | Logic validation`  
`Predestination Paradox | High | Complex scenario`

`**Research Requirements:**`  
`Review Novikov Self-Consistency Principle (due Week 1 Day 3)`  
`Document 5 paradox scenarios with examples (due Week 1 Day 5)`  
`Create paradox probability model (0.0-1.0 scale) (due Week 2 Day 2)`  
`Define 10 edge cases for testing (due Week 2 Day 4)`  
`Research quantum entanglement temporal aspects (due Week 3)`

`### 3.4 DevOps's Implementation Analysis`

`**Infrastructure Requirements:**`

`| Component | Technology | Configuration |`  
`|-----------|------------|---------------|`  
`| Version Control | GitHub | Branch protection |`  
`| CI/CD | GitHub Actions | Python 3.8+ |`  
`| Documentation | MkDocs | Material theme |`  
`| Testing | pytest | Coverage reporting |`  
`| Dependencies | pip | requirements.txt |`

`**CI Pipeline:**`  
```` ```yaml ````  
`# .github/workflows/ci.yml`  
`name: TS-Com CI`  
`on:`   
  `push:`  
    `branches: [ main, develop ]`  
  `pull_request:`  
    `branches: [ main ]`

`jobs:`  
  `test:`  
    `runs-on: ubuntu-latest`  
    `strategy:`  
      `matrix:`  
        `python-version: [3.9, '3.10']`  
      
    `steps:`  
      `- uses: actions/checkout@v2`  
        
      `- name: Setup Python ${{ matrix.python-version }}`  
        `uses: actions/setup-python@v2`  
        `with:`  
          `python-version: ${{ matrix.python-version }}`  
        
      `- name: Install dependencies`  
        `run: |`  
          `python -m pip install --upgrade pip`  
          `pip install -r requirements.txt`  
          `pip install pytest pytest-cov flake8 black`  
        
      `- name: Check code style with black`  
        `run: black --check src/`  
        
      `- name: Lint with flake8`  
        `run: flake8 src/ --count --max-complexity=10 --statistics`  
        
      `- name: Test with pytest`  
        `run: pytest tests/ --cov=src --cov-report=xml --cov-report=html`  
        
      `- name: Upload coverage report`  
        `uses: actions/upload-artifact@v2`  
        `with:`  
          `name: coverage-report`  
          `path: htmlcov/`

### 3.5 Tester/QA's Implementation Analysis

**Test Strategy:**

**Test Levels:**

1. **Unit Tests** (Week 2\)  
     
   - Individual class testing  
   - Method-level validation  
   - Expected: 50+ test cases  
   - Coverage target: \>80%

   

2. **Integration Tests** (Week 3\)  
     
   - Layer interaction testing  
   - End-to-end packet flow  
   - Expected: 20+ scenarios  
   - Focus on interface contracts

   

3. **System Tests** (Week 4\)  
     
   - Full simulation testing  
   - Performance benchmarks  
   - Expected: 10+ test runs  
   - Response time \<1s per operation

**Test Matrix:** 

| Component | Unit Tests | Integration Tests | System Tests | Total | Owner |
| :---- | :---- | :---- | :---- | :---- | :---- |
| CAAP | 15 | 5 | 2 | 22 | Tester (ธนินธร) |
| TRP | 20 | 8 | 3 | 31 | Tester (ธนินธร) |
| PPP | 15 | 5 | 3 | 23 | Tester (ธนินธร) |
| Simulation | 10 | 2 | 2 | 14 | Tester (ธนินธร) |
| Total | 60 | 20 | 10 | 90 |  |

**Bug Tracking Template:**

`## Bug Report`  
`**ID:** TSCOM-[Number]`  
`**Date:** [Date]`  
`**Reported By:** [Name]`  
`**Component:** [CAAP/TRP/PPP/Simulation/Integration]`

`**Severity:**`   
`- [ ] Critical (Blocks progress, no workaround)`  
`- [ ] High (Major feature broken)`  
`- [ ] Medium (Minor feature broken)`  
`- [ ] Low (Cosmetic issue)`

`**Description:**`  
`[Clear description of the bug]`

`**Environment:**`  
`- Python Version:`   
`- OS:`   
`- Branch/Commit:`   
`- Test Scenario:` 

`**Steps to Reproduce:**`  
`1.`   
`2.`   
`3.` 

`**Expected Behavior:**`  
`[What should happen]`

`**Actual Behavior:**`  
`[What actually happens]`

`**Screenshots/Logs:**`

---

## Part 4: Daily Standup Template

## **`What I did yesterday:`**

Architect (ศุภกร กรมรินทร์): Designed initial layered architecture and reviewed documentation structure.

Engineer (ณภัทร อรัญพูล): Set up project repository and initialized frontend/backend skeleton.

Specialist (ณัฐกรณ์ อินธิสาร): Researched AI semantic interpretation approaches and defined 3 use cases.

DevOps (ณัชพล เพ็งพล): Prepared deployment environment and configured basic CI workflow.

Tester (ธนินธร อันทรบุตร): Drafted initial test plan and reviewed system requirements.

`-`

## **`What I'll do today:`**

Architect (ศุภกร กรมรินทร์): Finalize Architecture\_Spec.md and create high-level diagrams.

Engineer (ณภัทร อรัญพูล): Implement file upload API and basic UI layout.

Specialist (ณัฐกรณ์ อินธิสาร): Prototype semantic\_interpreter logic (rule-based version).

DevOps (ณัชพล เพ็งพล): Setup staging deployment (Vercel \+ backend host).

Tester (ธนินธร อันทรบุตร): Create test cases for upload and analysis pipeline.

`-`

## **`Blockers:`**

`Dataset availability for animal sounds – Specialist`

`Deployment platform limitations (free tier constraints) – DevOps`

`-`

## **`Progress Metrics:`**

`Tests passing: 2/10`

`Components integrated: 1/5`

`Documentation complete: 35%`

`Days until deadline: 28`

---

## Part 5: Sprint Review Checklist

### End of Sprint 1 (Week 1\)

* Architecture approved  
* Environment working  
* Test framework ready  
* All specs documented  
* Team velocity measured

### End of Sprint 2 (Week 2\)

* Core protocols implemented  
* Unit tests passing  
* Components run independently  
* Code reviewed

### End of Sprint 3 (Week 3\)

* All components integrated  
* End-to-end flow working  
* Demo scenarios ready  
* Visualization functional

### End of Sprint 4 (Week 4\)

* All deliverables ready  
* Documentation complete  
* Presentation prepared  
* Submission package assembled

---

## Part 6: Contingency Plans

### Plan A: Behind Schedule

If behind by \>2 days:

1. Reduce scope (remove nice-to-have features)  
2. Increase pair programming  
3. Extend working hours (max \+2 hours/day)

### Plan B: Integration Failure

If integration fails:

1. Roll back to last working version  
2. Isolate problematic component  
3. Create simplified interface  
4. Re-integrate with mocks

### Plan C: Team Member Absence

If member absent \>2 days:

1. Redistribute tasks  
2. Pair programming covers gaps  
3. Adjust deliverables  
4. Document knowledge transfer

### Plan D: Technical Block

If technical issue blocks progress:

1. 2-hour investigation limit  
2. Escalate to team  
3. Seek instructor help  
4. Implement workaround

---

## Part 7: Success Criteria Sign-off

| Criteria | Target | Current | Owner | Status |
| :---- | :---- | :---- | :---- | :---- |
| Architecture approved | Week 1 |  | Architect | ⏳ |
| All components implemented | Week 2 |  | Engineer | ⏳ |
| Integration complete | Week 3 |  | DevOps | ⏳ |
| Tests passing (\>80% coverage) | Week 4 |  | Tester | ⏳ |
| Demo ready | Week 4 |  | All | ⏳ |
| Documentation complete | Week 4 |  | All | ⏳ |
| Presentation prepared | Week 4 |  | All | ⏳ |

---

## Approval

| Role | Name | Signature | Date |
| :---- | :---- | :---- | :---- |
| Architect | ศุภกร กรมรินทร์ |  |  |
| Engineer | ณภัทร อรัญพูล |  |  |
| Specialist | ณัฐกรณ์ อินธิสาร |  |  |
| DevOps | ณัชพล เพ็งพล |  |  |
| Tester/QA | ธนินธร อันทรบุตร |  |  |

---

*This implementation plan is approved for the CP352005 Networks undergraduate project. All team members agree to follow this plan and report deviations immediately.*

**Plan Version:** v2.0  
**Last Updated:** \[Date\]  
**Next Review:** Daily standups, Weekly sprints

`---`

`These two documents provide a complete, role-assigned framework for the 4-week undergraduate project. The **architecture_spec.md** includes the architectural review with conditional approvals and required changes, while the **implementation_plan.md** provides detailed role-based analysis, daily schedules, and contingency planning. Both documents are ready for team use and instructor review.`

