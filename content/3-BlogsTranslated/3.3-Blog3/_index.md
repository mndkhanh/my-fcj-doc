---
title: "Accelerate AI agent development with the Nova Act IDE extension"
date: "2025-09-09T14:41:44+07:00"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

_Authors: [Donnie Prakoso](https://aws.amazon.com/blogs/aws/author/donnie/)_

_Published At: September 23, 2025_

_Categories: [Amazon Nova](https://aws.amazon.com/blogs/aws/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-nova/), [Announcements](https://aws.amazon.com/blogs/aws/category/post-types/announcements/), [Developer Tools](https://aws.amazon.com/blogs/aws/category/developer-tools/), [Launch](https://aws.amazon.com/blogs/aws/category/news/launch/), [News](https://aws.amazon.com/blogs/aws/category/news/)_

---

Today, I’m excited to announce the [Nova Act extension](https://github.com/aws/nova-act-extension) — a tool that streamlines the path to build browser automation agents without leaving your IDE. The Nova Act extension integrates directly into IDEs like Visual Studio Code (VS Code), Kiro, and Cursor, helping you to create web-based automation agents using natural language with the [Nova Act model](https://nova.amazon.com/act).

Here’s a quick look at the Nova Act extension in Visual Studio Code:
![Demo animation](/images/Blogs/3.3.1.gif)

The Nova Act extension is built on top of the [Amazon Nova Act SDK (preview)](https://labs.amazon.science/blog/nova-act), our browser automation agents SDK (Software Development Kit). The Nova Act extension transforms traditional workflow development by eliminating context switching between coding and testing environments. You can now build, customize, and test production-grade agent scripts—all within your IDE—using features like natural language based generation, atomic cell-style editing, and integrated browser testing. This unified experience accelerates development velocity for tasks like form filling, QA automation, search, and complex multi-step workflows.

You can start with the Nova Act extension by describing your workflow in natural language to quickly generate an initial agent script. Customize it using the notebook-style builder mode to integrate APIs, data sources, and authentication, then validate it with local testing tools that simulate real-world conditions, including live step-by-step debugging of lengthy multi-step workflows.

<u>**Getting started with the Nova Act extension**</u>

First, I need to install the Nova Act extension from the extension manager in my IDE.

I’m using Visual Studio Code, and after choosing Extensions, I enter Nova Act. Then, I select the extension and choose Install.
![Demo animation](/images/Blogs/3.3.2.png)

To get started, I need to obtain an API key. To do this, I navigate to the [Nova Act page](https://nova.amazon.com/act) and follow the instructions to get the API key. I select Set API Key by opening the Command Palette with
Press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> / <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>
![Demo animation](/images/Blogs/3.3.3.png)

After I’ve entered my API key, I can try Builder Mode. This is a notebook-style builder mode that breaks complex automation scripts into modular cells, allowing me to test and debug each step individually before moving to the next.

Here, I can use the [Nova Act SDK](https://github.com/aws/nova-act) to build my agent. On the right side, I have a Live view panel to preview my agent’s actions in the browser and an Output panel to monitor execution logs, including the model’s thinking and actions.
![Demo animation](/images/Blogs/3.3.4.png)

To test the Nova Act extension, I choose Run all cells. This will start a new browser instance and act based on the given prompt.
![Demo animation](/images/Blogs/3.3.5.png)

I choose Fullscreen to see how browser automation works.
![Demo animation](/images/Blogs/3.3.6.png)

Another useful feature in Builder Mode is that I can navigate to the Output panel and select the cell to see its logs. This helps me debug or review logs specific to the cell I’m working on.
![Demo animation](/images/Blogs/3.3.7.png)

I can also select a template to get started.
![Demo animation](/images/Blogs/3.3.8.png)

Besides using Builder Mode, I can also chat with Nova Act to create a script for me. To do that, I select the extension and choose Generate Nova Act Script. The Nova Act extension opens a chat dialog in the right panel and automatically creates a script for me.
![Demo animation](/images/Blogs/3.3.9.png)

After I finish creating the script, I can choose Start Builder Mode, and the Nova Act extension will help me create a Python file in Builder Mode. This creates a seamless integration because I can switch between chat capability and Builder Mode.
![Demo animation](/images/Blogs/3.3.10.png)

In the chat interface, I see three workflow modes available:

- Ask: Describe tasks in natural language to generate automation scripts
- Edit: Refine or customize generated scripts before execution
- Agent: Run, monitor, and interact with the AI agent performing the workflow
  ![Demo animation](/images/Blogs/3.3.11.png)

I can also add Context to provide relevant information about my active documents, instructions, problems, or additional Model Context Protocol (MCP) resources the agent can use, plus a screenshot of the current window. Providing this information helps the agent understand any specific requirements for the automation task.
![Demo animation](/images/Blogs/3.3.12.png)

The Nova Act extension also provides a set of predefined templates that I can access by entering / in the chat. These templates are predefined automation scenarios designed to help quickly generate scripts for common web tasks.
![Demo animation](/images/Blogs/3.3.13.png)

I can use these templates (for example, @novaAct /shopping [my requirements]) to get tailored Python scripts for my workflow. At launch, Nova Act extension provides the following templates:

- /shopping: Automates online shopping tasks (searching, comparing, purchasing)
- /extract: Handles data extraction
- /search: Performs search and information gathering
- /qa: Automates quality assurance and testing workflows
- /formfilling: Completes forms and data entry tasks

This extension transforms my agent development workflow by positioning Nova Act extension as a full-stack agent builder tool—a complete agent IDE for the entire development lifecycle. I can prototype with natural language, customize with modular scripting, and validate with local testing—all without leaving my IDE—ensuring production-grade scripts.

<u>**Things to know**</u>

Here are key points to note:

- Supported IDEs: At launch, the Nova Act extension is available for Visual Studio Code, Cursor, and Kiro, with additional IDE support planned
- Open source: The Nova Act extension is available under the Apache 2.0 license, allowing for community contributions and customization
- Pricing: The Nova Act extension is available at no charge.

Get started with Nova Act extension by installing it from your IDE’s extension marketplace or visiting the [GitHub repository](https://github.com/aws/nova-act-extension) for documentation and examples.

---

## Authors

<div style="display:flex; gap:20px; margin-bottom:30px;">
  <img src="/images/Blogs/3.3.0.jpeg" alt="Rodolfo Brenes" style="width:110px; border-radius:4px;">
  <div>
    <h3>Donnie Prakoso</h3>
    <p>
      Donnie Prakoso is a software engineer, self-proclaimed barista, and Principal Developer Advocate at AWS. With more than 17 years of experience in the technology industry, from telecommunications, banking to startups. He is now focusing on helping the developers to understand varieties of technology to transform their ideas into execution. He loves coffee and any discussion of any topics from microservices to AI / ML.
    </p>
  </div>
</div>
