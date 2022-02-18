# XMLParser
Parsing an XML file with coding violations to a new format

Welcome,

This is a C++ program which converts an XML file containing coding violation suppressions to a new format.

The legacy version has the format of:

<?xml version="1.0" encoding="utf-8"?> (*********first line - encoding standard)
<Suppressions> (*******second line is constant)
  <Suppression class="com.parasoft.xtest.results.api.suppressions.CodingStandardSuppression" context="/Some/Absolute/Path/fileLocationOfFIrstSuppression.cpp" ctxStrg="ResCtx">
      <TestResultSuppressionData>
         <Reason>First Supression</Reason>
         <User>julio gutierrez</User>
         <Date>1553193102802</Date>
         <Message>First Message</Message>
         <Severity>3</Severity>
         <RuleId>PREPROC-14</RuleId>
         <TestId/>
      </TestResultSuppressionData>
   </Suppression>
</Suppressions> (******last line is constant)

Please note that line 10, 11, and 23 remain constant since they are the encoding standard and then define the beginning and end of all suppressions.

***One single instance of a suppression is shown from lines 12-22 and is repeated per each suppression that is present.

The new format (parasoft.suppress) is as follows:

suppression-begin
file: Account.cpp                 (required)
line: 12                          (optional)
rule-id: CODSTA-123               (optional)
message: Exact violation message  (optional)
reason: Approved                  (optional)
author: devel                     (optional)
date: 2020-09-21                  (optional)
suppression-end

Please note that all of the fields are optional except for the name of the file. Each new format of the suppression has the format written above.

The objective is converting each legacy suppression into the new format.

Instructions to Use the XMLParser Program:

1. Open your IDE of choice for running C++ applications.

2. Create a source file with the name of your choice (ex. main.cpp)

3. Copy the text written in the file "Script for parsing Suppression XML to Parasoft Suppress.txt" to your source file.

4. Next, add the "suppressions.xml" file to the same directory which contains the source file so that it is accessible to the applications.

5. Lastly, execute the source file in your IDE and the result is a generated "parasoft.suppress" file which has 72 newly formatted suppressions.

Thank you for reading and I hope that you enjoy my small side project.
