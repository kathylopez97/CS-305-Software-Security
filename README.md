# CS-305: Software Security

## Portfolio Reflection

This repository contains my Artemis Financial Vulnerability Assessment Report from Project One. During CS-305, I worked with Java, reviewed application code, and used security tools to identify potential vulnerabilities. Before working on these projects, I didn't realize how many security concerns could exist in an application that appears to work normally. I learned that developing secure software involves understanding potential risks, examining the code carefully, and knowing how to address weaknesses before they become bigger problems.

### 1. Who was the client, and what security issues needed to be addressed?

Artemis Financial was a financial services company that developed personalized plans for savings, retirement, investments, and insurance. Since the company handled sensitive financial and customer information, keeping that data protected was an important requirement.

The company wanted to modernize its existing application without introducing unnecessary security risks. My responsibility was to examine the Java code, identify vulnerabilities, and recommend improvements. During my review, I focused on concerns involving database credentials, input validation, error handling, and outdated dependencies. These issues mattered because they could expose private information or affect how the application worked.

### 2. What did I do well when identifying vulnerabilities, and why is secure coding important?

One thing I did well was looking beyond whether the application worked and considering what could happen if someone accessed or used it incorrectly. While reviewing the source code, I found database credentials stored directly in the program, missing input validation, and error-handling methods that could expose internal details. I also identified areas where access to customer information needed better restrictions.

I used OWASP Dependency-Check to examine security concerns involving third-party libraries. This helped me understand why manually reviewing code and using automated tools are both valuable.

Secure coding matters because a small weakness can create opportunities for unauthorized access or data exposure. For a financial services company, a security incident could also damage customer trust and disrupt its services. This project showed me why security needs attention throughout development, not just when something goes wrong.

### 3. Which part of the vulnerability assessment was challenging or helpful?

Working with OWASP Dependency-Check was one of the most helpful parts of Project One. My scan identified 13 vulnerable dependencies associated with 293 reported vulnerabilities. I was surprised by how many potential security problems could come from libraries already included in an application.

The harder part was understanding what those results actually meant. Finding a vulnerability in a report doesn't automatically mean someone can exploit it in the application. I had to consider how serious each issue was and whether the affected component was relevant to the software.

This helped me understand that identifying vulnerabilities is only the beginning. Developers also need to investigate the findings and decide which ones should be addressed first.

### 4. How did I increase layers of security, and how would I address vulnerabilities in the future?

In Project One, I recommended removing hard-coded database credentials, validating user input, limiting access to sensitive information, improving error handling, and replacing outdated libraries. Each recommendation addressed a different weakness found during the assessment.

Project Two gave me an opportunity to work with additional security features. I used SHA-256 to generate a checksum and configured HTTPS with a self-signed certificate. The checksum demonstrated how changes to data could be detected through a trusted comparison, while HTTPS provided encrypted communication during local testing. I also learned that a self-signed certificate isn't suitable for establishing trusted server identity in a production environment.

These projects showed me why applications need multiple security measures rather than depending on one solution. In future work, I would continue using code reviews, dependency scans, and testing to identify risks. I would also consider the severity and possible impact of each issue before deciding how to fix it.

### 5. How did I verify that the application was functional and secure after making changes?

In Project Two, I tested the application after making security-related changes. I ran it locally and accessed the `/hash` endpoint using HTTPS on port 8443. The application displayed a SHA-256 checksum, which I compared with a separately calculated result to confirm that the hashing process worked correctly.

I also reviewed the Java code and checked the application's behavior after updating Spring Boot to version 3.5.7. To look for remaining security concerns, I ran OWASP Dependency-Check again.

The reported vulnerability findings decreased from 837 to 685. However, the scans included different sets of dependencies, so I couldn't assume that all 152 fewer findings represented vulnerabilities that had been fixed.

One important lesson was that a successful test doesn't prove an application is completely secure. Even when a feature works, additional reviews and security testing may still be needed. I would continue checking the application after future changes to make sure improvements don't introduce new problems.

### 6. What tools, resources, and coding practices would help me in future projects?

OWASP Dependency-Check was especially useful because it allowed me to examine third-party components for reported vulnerabilities. Maven helped me manage dependencies and run security scans, while Java keytool allowed me to generate a certificate for local HTTPS testing.

I also used Java's MessageDigest class to implement SHA-256 hashing and gained experience configuring Spring Boot. These tools helped me connect what I learned about security to actual application development.

Another important part of the course was learning to pay attention to how information is handled. Protecting passwords, validating inputs, keeping dependencies updated, and testing changes are practices I want to continue using. I also plan to review my code more carefully instead of assuming that a working program is automatically secure.

### 7. What would I show future employers from this assignment?

I would share my Artemis Financial Vulnerability Assessment Report because it shows how I reviewed an existing application, identified potential security problems, and developed a plan to address them. The report includes my manual code review, OWASP Dependency-Check findings, and recommended improvements.

I would also discuss the work I completed in Project Two, including generating a SHA-256 checksum, configuring HTTPS, creating a security certificate, and testing the application. These examples demonstrate my experience working with security tools and applying what I learned to Java software.

Looking back, these projects helped me become more comfortable investigating technical problems and understanding why certain security measures are necessary. I would use this work to show employers how I approach software security, evaluate risks, and work toward making applications safer and more reliable.

