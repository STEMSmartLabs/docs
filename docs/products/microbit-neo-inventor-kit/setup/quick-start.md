# Setup

The **Neo Inventor Kit for BBC Microbit** works seamlessly with the official [Microsoft MakeCode Editor](https://makecode.microbit.org/). MakeCode provides a friendly, browser-based environment where you can program the micro:bit using **Blocks**, **JavaScript**, or **Python**—making it suitable for both beginners and advanced learners.

---

## Install the Neo Inventor kit for Microbit Makecode extension


1. Open [https://makecode.microbit.org](https://makecode.microbit.org) in your browser.  

   ![MakeCode Home Page](images/makecode-home.png)
2. Click on **New Project** and create a project.  

   ![MakeCode New Project](images/makecode-new-project.png)
3. In the MakeCode editor, click on the **Extensions** menu.  

   ![Open Extensions Menu](images/makecode-open-extensions.png)
4. In the search box, paste the GitHub URL:

   https://github.com/STEMSmartLabs/neo-inventor-kit-microbit
and press Enter, then click on the extension to install it.
![Install Extensions ](images/makecode-install-extension.png)


Once installed, you will see the Neo Inventor Kit category in the MakeCode blocks panel.

![Neo Inventor Kit Menu ](images/makecode-neo-inventor-kit-menu.png)

---

## Points to remember when using Neo Inventor Kit
1. Always initialize the kit by using **initialize Neo Inventor kit** in the **on start** block in all your projects.
![Neo Inventor Kit Initialize ](images/makecode-neo-inventor-kit-init.png)
2. It will disable microbit onboard LED since these pins are used by the Neo Inventor kit so duing the boot this initialization happens because of which you will see the fan and buzzer turning on and off.
3. Do not use the microbit onboard 25 LEDs in the projects which means do not use show blocks under the **Basic** category use only the OLED display blocks under **Neo Inventor Kit** category since it is now remapped.
---


✅ With MakeCode, the **Neo Inventor Kit for BBC Microbit** becomes a fast, flexible, and student-friendly platform for **electronics, coding, and real-world problem solving**.  
