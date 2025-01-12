# Comprehensive Summary of SWE 216: Software Requirements Engineering

## Table of Contents

- [Comprehensive Summary of SWE 216: Software Requirements Engineering](#comprehensive-summary-of-swe-216-software-requirements-engineering)
  - [Table of Contents](#table-of-contents)
    - [1. Why Requirements Engineering](#1-why-requirements-engineering)
    - [2. Introduction to Requirements](#2-introduction-to-requirements)
    - [3. How to Write Good Requirements](#3-how-to-write-good-requirements)
    - [4. Requirements Engineering in Software Development Life Cycles (SDLC)](#4-requirements-engineering-in-software-development-life-cycles-sdlc)
    - [5. System Vision, Context, and Requirements Engineering Framework](#5-system-vision-context-and-requirements-engineering-framework)
    - [6. Requirements Discovery](#6-requirements-discovery)
    - [7. Fundamentals of Goal Orientation](#7-fundamentals-of-goal-orientation)
    - [8. Fundamentals of Scenarios](#8-fundamentals-of-scenarios)
    - [9. Solution-Oriented Requirements](#9-solution-oriented-requirements)
    - [10. Requirements Prioritization and Agile Estimation](#10-requirements-prioritization-and-agile-estimation)
    - [11. Requirements Conflicts and Negotiation](#11-requirements-conflicts-and-negotiation)
    - [12. Requirements Validation](#12-requirements-validation)
    - [13. Fundamentals of Requirements Management](#13-fundamentals-of-requirements-management)
    - [14. Prototyping](#14-prototyping)
    - [15. Usability Requirements](#15-usability-requirements)
    - [Closing Notes](#closing-notes)

---

### 1. Why Requirements Engineering
- **Definition**: Requirements Engineering (RE) ensures that the right system is built by identifying and documenting stakeholders' needs and aligning them with technical solutions.
- **Key Roles**:
  - Bridge between stakeholders and developers.
  - Prevent project failures due to unclear requirements.
- **Challenges in RE**:
  - Ambiguity, complexity, changing needs, and conflicting requirements.
- **Benefits**:
  - Clear goals, better resource utilization, and increased stakeholder satisfaction.

---

### 2. Introduction to Requirements
- **What are Requirements?**
  - Statements describing what a system should do (functional) or how it should perform (non-functional).
- **Types of Requirements**:
  - **Functional Requirements**: Define system functionality (e.g., "The system shall allow users to log in.").
  - **Non-Functional Requirements**: Focus on performance, usability, and security (e.g., "The system must respond within 2 seconds.").
  - **Domain Requirements**: Constraints imposed by the system's operational environment.
- **Hierarchy**:
  - High-Level Requirements (broad goals).
  - Detailed-Level Requirements (specific implementation details).

---

### 3. How to Write Good Requirements
- **Characteristics of Good Requirements**:
  - **Clear and Concise**: Avoid vague terms like "user-friendly."
  - **Complete**: Covers all necessary aspects.
  - **Consistent**: Free from contradictions.
  - **Verifiable**: Can be tested or demonstrated.
- **Best Practices**:
  - Use active voice and standardized templates.
  - Focus on "what" the system should do, not "how."
- **Common Pitfalls**:
  - Ambiguity, mixing design details with requirements, and ignoring stakeholders.

---

### 4. Requirements Engineering in Software Development Life Cycles (SDLC)
- **Traditional SDLC Models**:
  - **Waterfall**: Sequential and rigid, suitable for stable projects.
- **Modern SDLC Models**:
  - **Agile**: Iterative and adaptive, prioritizing customer feedback.
  - **Spiral**: Combines iterative development with risk management.
- **Integration of RE in SDLC**:
  - Initial phases focus on elicitation and analysis.
  - Iterative phases ensure continuous validation and refinement.
- **Key Techniques**:
  - Use cases, user stories, and sprint planning in Agile.

---

### 5. System Vision, Context, and Requirements Engineering Framework
- **Vision Statement**:
  - A concise declaration of the system's goals and purpose.
  - Example Template:
    - "For [target customer] who [need], the [product name] is [category] that [key benefit]."
- **System Context**:
  - Defines boundaries between the system and its environment.
  - **System Boundary**: Separates what is part of the system from what is not.
  - **Context Boundary**: Distinguishes relevant external factors from irrelevant ones.
- **RE Framework**:
  - Three core activities: elicitation, negotiation, and documentation.

---

### 6. Requirements Discovery
- **Definition**: Identifying requirements through communication with stakeholders and analysis of existing systems.
- **Stakeholder Categories**:
  - **Customers/Clients**: Fund the project.
  - **Users**: Provide insights into usability and features.
  - **Domain Experts**: Ensure technical feasibility and domain relevance.
  - **Others**: Regulators, competitors, and interest groups.
- **Elicitation Techniques**:
  - Interviews (structured/unstructured).
  - Workshops (focus groups).
  - Ethnography (observing users in their environment).
  - Questionnaires and competitive analysis.

---

### 7. Fundamentals of Goal Orientation
- **Definition**: Goals define high-level objectives that guide requirements development.
- **Goal Types**:
  - **Hard Goals**: Concrete and measurable (e.g., system uptime).
  - **Soft Goals**: Non-measurable, quality-focused (e.g., user satisfaction).
- **Goal Modeling**:
  - Use AND/OR decomposition to break down complex goals.
  - Visualize using Goal-Oriented Requirements Language (GRL).

---

### 8. Fundamentals of Scenarios
- **Definition**: Scenarios describe interactions between users and the system.
- **Types of Scenarios**:
  - **Positive**: Successful execution of tasks.
  - **Negative**: Failures or errors during execution.
- **Documentation Techniques**:
  - Textual narratives.
  - UML Use Case Diagrams for user-system interactions.
  - Activity Diagrams for workflow visualization.

---

### 9. Solution-Oriented Requirements
- **Focus Areas**:
  - **Data Perspective**: Entities and relationships.
  - **Functional Perspective**: What the system should do.
  - **Behavioral Perspective**: How the system responds to events.
- **UML Diagrams**:
  - **Class Diagrams**: Define entities and their attributes.
  - **State Machine Diagrams**: Model object lifecycles.
  - **Sequence Diagrams**: Capture interactions.

---

### 10. Requirements Prioritization and Agile Estimation
- **Prioritization Techniques**:
  - **Pareto Principle**: Focus on the 20% of features generating 80% of value.
  - **$100 Test**: Allocate virtual money to prioritize features.
  - **Cost of Delay**: Quantify the impact of not delivering a feature.
- **Agile Estimation**:
  - Story Points: Quantify effort and complexity.
  - Planning Poker: Collaborative estimation process.
  - Velocity Tracking: Measure team output per sprint.

---

### 11. Requirements Conflicts and Negotiation
- **Common Conflict Types**:
  - **Data Conflicts**: Misunderstandings or errors.
  - **Interest Conflicts**: Differing stakeholder goals.
  - **Value Conflicts**: Diverging evaluation criteria.
- **Resolution Strategies**:
  - Negotiation: Consensus-building among stakeholders.
  - Creative Solutions: Innovative approaches to reconcile conflicts.
  - Decision Making: Higher authority resolves disputes.
- **Win-Win Negotiation**:
  - Focus on achieving mutual benefits.

---

### 12. Requirements Validation
- **Validation vs. Verification**:
  - Validation ensures the "right product" is being built.
  - Verification ensures the product is "built right."
- **Techniques**:
  - Simple Checks: Traceability, consistency, and completeness.
  - Prototyping: Early simulations for user feedback.
  - Checklist-Based Inspections: Identify missing or ambiguous requirements.

---

### 13. Fundamentals of Requirements Management
- **Key Activities**:
  - Change Management: Handle additions, modifications, and deletions.
  - Version Control: Track changes to requirements.
  - Traceability: Link requirements to artifacts like design and testing.
- **Stable vs. Volatile Requirements**:
  - Stable: Core functionalities unlikely to change.
  - Volatile: Context-dependent and subject to modification.

---

### 14. Prototyping
- **Purpose**:
  - Validate designs and gather feedback early in development.
- **Types**:
  - **Low-Fidelity**: Paper-based sketches and mock-ups.
  - **High-Fidelity**: Interactive and near-final versions.
  - **Horizontal**: Focus on user interface breadth.
  - **Vertical**: Focus on in-depth functionality.
- **Approaches**:
  - **Throwaway**: Discard after gathering feedback.
  - **Evolutionary**: Refine iteratively into the final system.

---

### 15. Usability Requirements
- **Definition**: Measures how effectively, efficiently, and satisfactorily users can interact with the system.
- **Key Factors**:
  - **Efficiency**: Speed and accuracy of task completion.
  - **Effectiveness**: Task completion rate.
  - **Satisfaction**: User contentment and ease of use.
  - **Error Tolerance**: Ability to recover from mistakes.
- **Design Strategies**:
  - Beginners: Tutorials and feedback.
  - Intermediates: Recognition-based interfaces.
  - Experts: Shortcuts and customization.

---

### Closing Notes
This refined summary incorporates detailed insights from all slides, ensuring comprehensive coverage for revision and practical application in software requirements engineering.

