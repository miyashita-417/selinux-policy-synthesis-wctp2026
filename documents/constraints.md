\# Detailed definitions of functional requirements and logical constraints



This document describes the full details of the functional requirements and logical constraints omitted from the paper due to space limitations.



---



（１）Functional requirements and constraints for PID file control

<br>

The functional requirements for PID file control are as follows:



・Traverse and search inside the parent directory.

・Write to the parent directory.

・Add a new file name to the parent directory.

・Remove a file name from the parent directory.

・Automatically transition the label to the PID file type when creating a file in the parent directory.

・Create a new PID file.

・Open the PID file.

・Write data to the PID file.

・Retrieve attributes of the PID file.

・Lock the PID file.

・Delete the PID file.



<br>



The above functional requirements for PID file control are defined as the logical constraint $\\phi\_{pid}$ as follows:



$\\phi\_{pid}$ = $(allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_run\\\_t}, \\texttt{dir}, \\texttt{search}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_run\\\_t}, \\texttt{dir}, \\texttt{write}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_run\\\_t}, \\texttt{dir}, \\texttt{add\\\_name}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_run\\\_t}, \\texttt{dir}, \\texttt{remove\\\_name}) = \\mathrm{True}) $

&nbsp;              $\\land (type\\\_transition(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_run\\\_t}, \\texttt{file}, \\texttt{mydaemon\\\_var\\\_run\\\_t}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_var\\\_run\\\_t}, \\texttt{file}, \\texttt{create}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_var\\\_run\\\_t}, \\texttt{file}, \\texttt{open}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_var\\\_run\\\_t}, \\texttt{file}, \\texttt{write}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_var\\\_run\\\_t}, \\texttt{file}, \\texttt{getattr}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_var\\\_run\\\_t}, \\texttt{file}, \\texttt{lock}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_var\\\_run\\\_t}, \\texttt{file}, \\texttt{unlink}) = \\mathrm{True}) $





---

（２）Functional requirements and constraints for configuration file reading

<br>

The functional requirements for the configuration file are as follows:



・Traverse and search inside the parent directory.

・Retrieve attributes of the parent directory.

・Open the configuration file.

・Read the contents of the configuration file.

・Retrieve attributes of the configuration file.



<br>



The above functional requirements for configuration file reading are defined as the logical constraint $\\phi\_{conf}$ as follows:



$\\phi\_{conf}$ = $(allow(\\texttt{mydaemon\\\_t}, \\texttt{etc\\\_t}, \\texttt{dir}, \\texttt{search}) = \\mathrm{True}) $

&nbsp;               $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{etc\\\_t}, \\texttt{dir}, \\texttt{getattr}) = \\mathrm{True}) $

&nbsp;               $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_conf\\\_t}, \\texttt{file}, \\texttt{open}) = \\mathrm{True}) $

&nbsp;               $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_conf\\\_t}, \\texttt{file}, \\texttt{read}) = \\mathrm{True}) $

&nbsp;               $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_conf\\\_t}, \\texttt{file}, \\texttt{getattr}) = \\mathrm{True}) $



---

（３）Functional requirements and constraints for log file recording

<br>

The functional requirements for the log file are as follows:



・Traverse and search inside the parent directory.

・Write to the parent directory.

・Add a new log file name to the parent directory.

・Automatically transition the label to the log file type when creating a file in the parent directory.

・Create a new log file.

・Open the log file.

・Retrieve attributes of the log file.

・Append data to the log file.



<br>



The above functional requirements for log file recording are defined as the logical constraint $\\phi\_{log}$ as follows:



$\\phi\_{log}$ = $(allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_log\\\_t}, \\texttt{dir}, \\texttt{search}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_log\\\_t}, \\texttt{dir}, \\texttt{write}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_log\\\_t}, \\texttt{dir}, \\texttt{add\\\_name}) = \\mathrm{True}) $

&nbsp;              $\\land (type\\\_transition(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_log\\\_t}, \\texttt{file}, \\texttt{mydaemon\\\_log\\\_t}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_log\\\_t}, \\texttt{file}, \\texttt{create}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_log\\\_t}, \\texttt{file}, \\texttt{open}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_log\\\_t}, \\texttt{file}, \\texttt{getattr}) = \\mathrm{True}) $

&nbsp;              $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_log\\\_t}, \\texttt{file}, \\texttt{append}) = \\mathrm{True}) $



---

（４）Common functional requirements and constraints

<br>

The common requirements to reach the log file and PID file are as follows:



・Traverse and search inside the upper directory.

・Retrieve attributes of the upper directory.



<br>



The above common requirements are defined as the logical constraint $\\phi\_{common}$ as follows:



$\\phi\_{common}$ = $(allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_t}, \\texttt{dir}, \\texttt{search}) = \\mathrm{True}) $

&nbsp;                 $\\land (allow(\\texttt{mydaemon\\\_t}, \\texttt{var\\\_t}, \\texttt{dir}, \\texttt{getattr}) = \\mathrm{True}) $



---

（５）Functional requirements and constraints for network listening

<br>

The functional requirements for network listening are as follows:



・Create a TCP socket.

・Change socket settings.

・Bind a port to the socket.

・Use the port type $\texttt{http\_cache\_port\_t}$.

・Use the node type $\texttt{node\_t}$.

・Listen for connections.



<br>



The above functional requirements for network listening are defined as the constraint $\\phi\_{net}$ as follows:



$\\phi\_{net}$ = $(allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_t}, \\texttt{tcp\\\_socket}, \\texttt{create}) = \\mathrm{True}) $

&nbsp;              $\\land$ $(allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_t}, \\texttt{tcp\\\_socket}, \\texttt{setopt}) = \\mathrm{True}) $

&nbsp;              $\\land$ $(allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_t}, \\texttt{tcp\\\_socket}, \\texttt{bind}) = \\mathrm{True}) $

&nbsp;              $\\land$ $(allow(\\texttt{mydaemon\\\_t}, \\texttt{http\\\_cache\\\_port\\\_t}, \\texttt{tcp\\\_socket}, \\texttt{name\\\_bind}) = \\mathrm{True}) $

&nbsp;              $\\land$ $(allow(\\texttt{mydaemon\\\_t}, \\texttt{node\\\_t}, \\texttt{tcp\\\_socket}, \\texttt{node\\\_bind}) = \\mathrm{True}) $

&nbsp;              $\\land$ $(allow(\\texttt{mydaemon\\\_t}, \\texttt{mydaemon\\\_t}, \\texttt{tcp\\\_socket}, \\texttt{listen}) = \\mathrm{True}) $
