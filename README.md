# Development_issues_Solutions
This is a git branch where we can find proper solutions for issues that we are facing in Dev actitivities

**Q1** How to Kill 8080 process to get rid of following issue?
**Issue Description**
                Error starting ApplicationContext. To display the conditions report re-run your application with 'debug' enabled.
                2021-09-30 16:47:33.984 ERROR 9416 --- [           main] o.s.b.d.LoggingFailureAnalysisReporter   : 

                ***************************
                APPLICATION FAILED TO START
                ***************************

                Description:

                Web server failed to start. Port 8080 was already in use.

                Action:

                Identify and stop the process that's listening on port 8080 or configure this application to listen on another port.
 **Answer**<br>**Solution** <br>
               Step1: Run cmd like Run as administrator-->type the command **_netstat -a -o -n_** and now you will see the list of process running here <br>
               Step2: see the processid corresponding to local Address <br>
                **Proto  Local Address          Foreign Address        State           PID**  <br>
               **TCP      0.0.0.0:8080           0.0.0.0:0              LISTENING       4128**__  <br>
               Step3: Take the processid and run the below command <br>
               C:\WINDOWS\system32>**taskkill /F /PID 4128**  <br>
                SUCCESS: The process with PID 4128 has been terminated. <br>
**Workaround** <br>
              If you are using springBoot Application then in properties file you can add a different port like below <br>
               **server.port:2021  or server.port=2021**
