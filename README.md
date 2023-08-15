https://youtrack.jetbrains.com/issue/KTIJ-24448/Maven-IDE-Kotlin-facet-resets-the-custom-JDK-of-the-new-module

How to reproduce bug in Intellij Idea (2023.2):
* ... import project from existing sources as Maven project ...
* (Menu) File -> Project structure -> Project Setting -> Project -> SDK 
  * set 1.8 version
* (Menu) File -> Project Structure -> Project Settings -> Modules -> idea-java -> Dependencies -> Module SDK 
  * set to 11
* (Menu) File -> Project Structure -> Project Settings -> Modules -> idea-kotlin -> Dependencies -> Module SDK
  * set to 11
* Maven Tool window -> Reload all maven projects icon
* (Menu) File -> Project Structure -> Project Settings -> Modules -> idea-java -> Dependencies -> Module SDK ->
  * stays set to 11
* (Menu) File -> Project Structure -> Project Settings -> Modules -> idea-kotlin -> Dependencies -> Module SDK 
  * **is resets Module SDK to java 8 (probably from Project SDK)**
