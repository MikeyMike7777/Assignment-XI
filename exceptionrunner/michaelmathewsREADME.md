Tasks to answer in your own README.md that you submit on Canvas:

1. See logger.log, why is it different from the log to console?
   1. Console logging is set to INFO level and File logging is set to the ALL level in logger.properties
2. Where does this line come from? FINER org.junit.jupiter.engine.execution.ConditionEvaluator logResult Evaluation of condition [org.junit.jupiter.engine.extension.DisabledCondition] resulted in: ConditionEvaluationResult [enabled = true, reason = '@Disabled is not present']
   1. This message comes from the Java logger which checks each JUnit test to see if it is disabled before that test is run
3. What does Assertions.assertThrows do?
   1. execution of the code or lambda expression throws an expected exception of an expected type
4. See TimerException and there are 3 questions
    1. What is serialVersionUID and why do we need it? (please read on Internet)
       1. serialVersionUID is an identifier that is used to serialize/deserialize an object of a Serializable class. We need it to help us remember versions of a Serializable class to verify that a loaded class and the serialized object are compatible.
    2. Why do we need to override constructors?
       1. We need to override constructors for custom Exception extensions to set the causing exception and provide a benefit compared to the available standard exceptions
    3. Why we did not override other Exception methods?	
       1. The other Exception methods do not implement the serialVersionUID and therefore did have additional information necessary to be added to the default Exception Constructor
5. The Timer.java has a static block static {}, what does it do? (determine when called by debugger)
   1. It initializes the configuration file to be used in Timer.java (logger.properties) when using a Timer class
6. What is README.md file format how is it related to bitbucket? (https://confluence.atlassian.com/bitbucketserver/markdown-syntax-guide-776639995.html)
   1. A README.md file is a Markdown file format file that describes a directory
   2. Bitbucket Data Center uses Markdown for formatting text
7. Why is the test failing? what do we need to change in Timer? (fix that all tests pass and describe the issue)
   1. Test is failing because a null pointer exception is being thrown. If "timeNow" excecutes an exception, then "timeNow" is never initialized and is therefore null. We need to initialize "timeNow" before a possible exception can be thrown.
8. What is the actual issue here, what is the sequence of Exceptions and handlers (debug)
   1. The logger messages are being printed even when the method throws an exception, but these messages should only be printed when the test is sucessful
9. Make a printScreen of your eclipse JUnit5 plugin run (JUnit window at the bottom panel)
10. Make a printScreen of your eclipse Maven test run, with console
11. What category of Exceptions is TimerException and what is NullPointerException
    1. TimerException is in the Checked Exceptions catagory and it is an InterruptedException
    2. NullPointerException is a runtime exception (unchecked) when a variable is accessed which is not pointing to any object
12. Push the updated/fixed source code to your own repository.