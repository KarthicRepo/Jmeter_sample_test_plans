# Jmeter_sample_test_plans
Jmeter test plan samples covering most of the available components.


# JMETER SAMPLE PROJECTS

These set of Jmeter test plans covers a sample usage of almost all the components available in Jmeter tool.
I've used the Jmeter version 5.0 for creating all these test plans.

These test plans cover the below items in Jmeter.

##THREAD GROUPS:
- serial and parallel executions
- total users/threads, looping, rampup time.

##CONTROLLERS
- Simple controller
- Transaction controller
- Loop controller
- Runtime controller
- Throughput controller
- Once only controller
- Interleave controller
- Random controller
- Random-order controller
- Switch controller
- ForEach controller
- If controller

##TIMERS
- Constant timer
- Gaussian Random timer
- Uniform Random timer
- Constant throughput timer
- Synchronizing timer

##SAMPLER
- HTTP sampler

##LISTENER
- View Result Tree
- View Result Table
- Aggregate Report
- Summary Report

##POST-Processors
- Regex expression extractor

##OTHERS
- Distributed testing
- NON-UI based testing
- Dynamic server and load using commandline parameters


## Quick command reference 
```
//standalone instance in non-ui mode
jmeter.bat -n -t NoGuiModeTests.jmx -JSERVER=dummy.restapiexample.com -JTHREAD=5 -JLOOP=10 -e -o .\html -l testresults.jtl

//remote execution in master-slave configuration.
jmeter-server.bat
jmeter.bat -n -t NoGuiModeTests.jmx -JSERVER=dummy.restapiexample.com -JTHREAD=5 -JLOOP=10 -e -o .\html -l testresults.jtl -R 192.168.21.98

Where -n = non-gui mode
	  -t= testplan file name
	  -Jxxxx= command line parameter to the test plan variable
	  -e= export html report
	  -o= output file directory.
	  -R=remote server/slave ips
	
// generate html reports using csv results.  
jmeter.bat -g aggregatereport.csv -o .\test

Where  -g= generate html report from existing csv file
	   -o=output directory.

// BeanShell quick guide.	
prev.getResponseDataAsString()

vars.put("ResponceData", prev.getResponseDataAsString());
log.info(vars.get("ResponceData"));
Vars.putObject("objectName", list)

props.put("name", value)
Props.get("name")

log.info("Previous Response Message is: " + ctx.getPreviousResult().getResponseMessage());
log.info("Previous Response Code is: " + ctx.getPreviousResult().getResponseCode());
log.info("Previous Response URL is: " + ctx.getPreviousResult().getURL());
log.info("Previous Response Time is: " + ctx.getPreviousResult().getTime());

```
