# GWT Sample to work within IntelliJ
Application created from scratch with IntelliJ and an external tomcat application server

## Artifacts
1. _gwt-idea-sample:Web exploded DevMode_: Generate exploded directory with GWT compiled application
1. _gwt-idea-sample:Web exploded DevMode_Generate exploded directory without GWT compiled application

IntelliJ create automatically following Run Configurations:
![Run Configurations](Configurations.png?raw=true)
1. _Tomcat 9.0.38_: Start the given application server with current compiled classes
1. _Tomcat 9.0.38 DevMode_: Start the given application server with current compiled classes and one for artifact with DevMode
** created compile GWT module at `out\artifacts\gwt_idea_sample_Web_exploded`
** created Dev Mode compatible output at `out\artifacts\gwt_idea_sample_Web_exploded_DevMode`
   
1. _MySampleApplication_: Start Super Dev and Jetty instance server
1. _MySampleApplication NoServer_: Start Super Dev only and change the directory into which deployable output files will be written
1. Compund _MySampleApplication NoServer with Tomcat 9.0.38 DevMode_: Combines both launcher to one

## Steps to Debug
1. Launch `MySampleApplication NoServer with Tomcat 9.0.38 DevMode`
2. A Browser will open Url: `http://127.0.0.1:8080/MySampleApplication.html` But this will not work because the artifatc deployed to Path
![Deploy Path](Configurations_Deploy.png?raw=true)
2. Open Url `http://localhost:8080/gwt_idea_sample_Web_exploded_DevMode/MySampleApplication.html`
The the application should compile on the fly.

As Alternative you can change the Application Contect od Dev Mode Tomcat Launcher to `/`
I've create the configuration: _MySampleApplication NoServer with Tomcat 9.0.38 DevMode (ROOT)_
![Deploy Path](Configurations_Deploy_ROOT.png?raw=true)

see: http://www.gwtproject.org/doc/latest/DevGuideCompilingAndDebugging.html#DevGuideCompilerOptions
