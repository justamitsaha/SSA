
**System Development Life Cycle (SDLC)**  The **System Development Life Cycle (SDLC)** is the overall multi-step process of developing, implementing, and retiring information systems, progressing through initiation, analysis, design, implementation, maintenance, and disposal. **Requirements gathering** is the most critical initial step of this process, during which stakeholders define what the system needs to do and establish security requirements. Security must be involved as early as possible in the project lifecycle.

**Security Requirements Gathering**  Loosely based on the CLASP security requirements gathering process, an effective security requirements phase must answer three critical questions:

-   **What critical assets and services need protection?** You must identify the core components to secure. In a financial system example, this includes protecting financial data stored in the backend database, securing the requests and responses between the client, server, and database, and safeguarding server resources.
-   **How should user roles and privileges be defined?** Systems must categorize users by access level. For instance, a system might divide users into Regular Users (who can only read database data), Financial Administrators (who can read and write database data), and System Administrators (who modify server resources and perform backups).
-   **What is the attack surface?** You must identify all points where unauthorized users could enter or extract data, such as user interfaces (UI) and APIs accessed over HTTP.

**Threat Modeling: Data Flow and Trust Boundaries**  To create a functional threat model, you must map out how the system operates using a **Data Flow Diagram (DFD)**. A DFD illustrates how data moves through various parts of the system, such as a client making a request to a web server, the web server sending SQL queries to a database, and the data returning back along that chain.

Once the data flow is mapped, you must establish **Trust Boundaries** to analyze how data flows from non-trusted networks into the system. For example, a web server might reside on a trusted, on-premises network, while the client sits on an external network (the internet) and the database is hosted on an external cloud provider network.

**The STRIDE Method**  After mapping data flows and trust boundaries, the **STRIDE method** is used to brainstorm an initial list of threat vectors and vulnerabilities to finalize the security requirements. STRIDE is a mnemonic that stands for:

-   **Spoofing (S):** Can a malicious user pretend to be a different user?
-   **Tampering (T):** Can a malicious user modify data used by the system?
-   **Repudiation (R):** Can a malicious user deny that they performed an action that altered the system's state?
-   **Information Leakage (I):** Can a malicious user extract information that is supposed to be kept secret?
-   **Denial of Service (D):** Can a malicious user exhaust the system's resources to the point where it no longer functions as intended?
-   **Elevation of Privilege (E):** Can a malicious user inappropriately increase their ability to interact with system resources?