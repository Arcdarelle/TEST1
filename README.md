Q21 : Tuned
===========

[RedHat Exam Preparation](https://utrains.org/courses/redhat-exam-preparation/)  [Q21 : Tuned](https://utrains.org/lessons/q21-tuned-2/)In Progress

**Question 20.** Configure recommended tuned profile

**Answer**

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   # check if tuned is install, if not, install, start and enable itrpm -qa tuned  systemctl status tuned# check the active profile  tuned-adm active# list the available profiles   tuned-adm list# check the recommended profile  tuned-adm profile recommend# the recommended profile here is virtual-guest# To activate the recommended profiletuned-adm profile virtual-guest   `
