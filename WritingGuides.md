# How do you structuture your lab manuals

## Overview of the lab
 - Provide an overview of the lab in 5-10 lines. This could be one or more of the following:       
			1. Introduce a product/service/capability        
			2. Business case and how it is addressed in this lab
- Content of the lab        
			1. 3-5 bullet points on what the reader will learn from the lab    
			1. Should be something high level  and focus of the lab(not like you will learn how to login to Azure portal unless that is the purpose of the lab)
- Pre-requisites                    
			1. State what are the pre-requisites of the lab        
			1. Present options on how they can be acquired easily (for instance, launch on HoL, Sign up for Azure Free trial, get a VM from Marketplace, download and install, etc..)        
			1. Include "Launch lab on HOL " if the lab is available on platforms like LODS      
      
## Content
		○ Short and simple labs have more reach and usage compared to lengthy ones; If too long think of breaking into different labs  
		○ Divide the lab steps into multiple sections/exercises 
		○ Each section/exercise should have max of 10-12 steps
		○ Number your steps so it is easy for the readers to keep track of progress
		○ Keep information (notes, warnings) separate from activities. For instance, in the example below, an activity is combined with an informational statement
			§ Bad example - The remote desktop should have the "Windows Subsystem for Linux" installed, which allows you to run Linux binaries natively on top of the Windows kernel, including OpenSSH. You can choose what Linux distribution to use; the remote desktop has Ubuntu pre-configured. To open it, click on the Windows start button, then type "Ubuntu" and select the first result.
			
		○ Maintain a good balance between over sharing and under sharing for each step. 
			§ Example 1: Step 3: Click and select the "Always on" option
				□ Correction:  This is underexplain. You should educate readers instead of just asking to repeat steps. Step 3: Click and select the "Always on" option. The  Always On option for Availability Groups maximizes the availability of a set of user databases for an enterprise.
			§ Example 2 : The first piece of data is the Account URL. Currently, all Visual Studio Team Services accounts live within the top-level visualstudio.com domain. The account name you choose could be something personal, like your name, or something more work-related, like your company name. If you do intend to set up your account to share with others at your organization, you might want to coordinate this with those in your organization that manage your servers and infrastructure.
				□ Correction: Avoid overexplaining
		○ Screenshots helps readers to visualize and as well as validate if they have got to the steps correctly. But too many screenshots can not only make the lab look very long but also can quickly get the lab obsolete as UI of products can change quickly
		○ Decide "we" vs "you" - There is no definitive answer to which one is better. Choose one or the other and do not mingle. Personally, my choice is "We "as "We" sounds collective vs a personal "You".  
		○ 
	## Conclusion
		○ It is always good to end your lab with a summary of what readers learnt from the lab  and/or how the solution helps solves a particular person
		
