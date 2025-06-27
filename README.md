Read Me for STIG Re-automation repository



This script was made necessary by gross incompetence and sheer hubris. 

Hope it helps :)













I worked on White Sands Missile Range for a company that was contracting with the Enterprise Services Branch, basically the IT department, with the responsibility to manage almost the entire IT infrastructure for more than 2000 user systems, servers, and printers. In the defense environment, there are many rules and regulations to follow, with various tools designed to audit your enterprise's security posture and adherence to policy. One such report is the Security and Technical Implementation Guide (STIG), and the tool used to generate reports on compliance being evaluate STIG (eSTIG). The tools are distributed, updated, and reviewed by the Defense Information System Administration (DISA). 

Now, eSTIG is actually a really nifty tool. It uses shell scripting, powershell and Linux both, to run commands on a system, document the output, and in other ways report on the findings. It can do this for the operating system and any *common* software for which DISA has released a STIG. The STIG is supposed to stand as a guide, both for explaining how to set things up for user convenience and for security, with in-depth explanations as to the what and why for each rule, and references to the governing policy. Sometimes a single workstation would have 8 or 9 STIGs applied to it by eSTIG for things like Adobe Acrobat, Microsoft Edge, Windows 11 OS, MS 365, .net4 applications, and more. hundreds of other possibilities, actually. 

eSTIG also has customizable attributes through a file type called an Answer File. An answer file allows system administrators to write automated comments, change finding details, and even change the status of a rule based on the attributes of a rule ID. For example, eSTIG would always leave a rule titled 'Google Chrome must be a supported version' as 'not reviewed,' requiring SA input just to change the finding and comment that the version is fine. We automatically reboot workstations daily with a scheduled task, and know for a fact google is up to date, so we created an answer file that changed the status to Not a Finding, and comment that the version is up to date. This tool is designed to automate almost the entire workflow, requiring nothing more than review, remediation where necessary, and then submittal to auditors. 

Well, due to White Sands Missile Range's relatively remote location (45 minute minimum commute from either El Paso or Las Cruces), WSMR has becoming a breeding ground for nepotism, favoritism, massive and fragile egos, and gross incompetence at the highest level. A few such examples of gross incompetence at the highest levels includes the Enterprise Services Branch Chief and the System Owner. When we began to provide accurate and automated STIG Checklists to these two, they understood almost nothing. They were angry that we were using automated tools to change the statuses without reviewing them. They claimed we couldn't possibly know without checking. When I tried to explain how the answer files work, their incompetence showed itself to be the driving force in their lives. They added requirements to the STIGing process that dramatically increased the amount of time it would take to complete a STIG. They then required that we run eSTIG and provide the results with all of the silly, insane rules that they set up (not all of which are included here) to slow the process on 100% of the network by the end of the year. We were struggling to get 300 done in a quarter, due almost exclusively to their gross incompetence and fear for automation. So, what is a system administrator to do? 

Since these FUDs were as immovable on their 'standards' as they are incompetent, the only solution was to re-automate what they had made manual. So began the scripting and testing of scripts to fix this mess. The result is what I have provided here. A script that will apply a 'signature' to the comments of all rules that were modified by my answer files, sort the machines into categories of 'complete' - where all findings have a comment - or 'review' - which have open or not reviewed findings that do not have an automated comment. These scripts allowed me and my team to get back on track. 

Until they fired me. 

So now I am making my tools available to everyone in the world *except for the Enterprise Services Branch, the Information System Security Officer, any ISSO or ISSM, or DOD employee on White Sands Missile Range.* Government contractors on WSMR may use these scripts. I'll admit, I haven't done anything revolutionary here. It's a simple script. They could recreate it, easily, and I couldn't stop them. It is what it is. 

Thanks for reading. Good luck out there, folks. 
