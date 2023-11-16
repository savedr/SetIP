# SetIP
A batch script to set either DHCP or a variety of static IPs on Windows without futzing about with Settings!

To set up:

1. Find out the name Windows uses to refer to your computer's Ethernet adapter. 

An easy way to do this is to open up a Command Prompt window and run "ipconfig". Look for the section with
your Ethernet adapter, it should say "Ethernet adapter <name>:" where <name> is the name you want. This 
varies with the hardware you have installed or the ethernet driver software probably, mine is just 
"Ethernet" but you might have a different one here. Make a note of it.

2. Open up "setIP.bat" in a text editor, and change some text on 2 lines.

On Windows, the easiest way to do this is just with Notepad, unless you're a Hacker-Type and have some other 
bespoke text editor installed, in which case why are you even reading this sentence, lol. If you downloaded 
this project's files, just go to where you downloaded them to, and right-click the "setIP.bat" file, and 
choose "Edit". That should open it in Notepad like we want; you can also open Notepad first, click File 
menu, then Open, and browse to "setIP.bat" that way.

Scroll down until you see a line with the text ":setIP" on it, with that colon. Three lines below that, 
there's a line with the text "netsh interface ipv4 set address name="Ethernet" dhcp". Where "Ethernet" is, 
between those two quotation marks, erase Ethernet and type in the name Windows has for your Ethernet 
adapter.

Four more lines down is a line with somewhat similar text that reads "netsh interface ipv4 set address 
name="Ethernet".. etc. Same thing here, where it says "Ethernet", erase that and type in the 
name of your Ethernet adapter between the quotes.

3. Save the updated file. 

Now, in your text editor, Save this file so it overwrites the original "setIP.bat". With Notepad, since 
you Opened it originally, it should be set to save it as a custom file type (like ".bat") already, instead 
of the normal ".txt" file. 

4. Create a desktop shortcut with Administrator rights to run setIP.

Using your file manager, open the folder where the "setIP.bat" file is. Right-click the file, mouse over the 
"Send to" option, and click "Desktop (create shortcut)". Then, go to your Desktop and find the shortcut 
we just created, it should be named "setIP.bat - Shortcut". Right-click it, then choose Properties. On the 
Shortcut tab in this new window, click the "Advanced.." button. On the new pop-up window, click On the 
checkbox labeled "Run as administrator" and several other lines of text. Then click Ok to close that window, 
and Ok on the Properties window. 

That's it! 

To use it, just double-click that shortcut, and click "Yes" when Windows asks if you "want to allow this 
app to make changes to your device". (This Run as Administrator stuff is necessary for the command that 
sets your IP address to work.) Then, go through the program and it'll do its stuff!

If not, please get back to me here on git (github.com/savedr/SetIP), or email me at savedr@gmail.com.

Thanks so much for using this!
-savedR


===================================================================================================

About setIP:

This branch "modular" has basically the same functionality as SetIP-old, except instead of including the actual 
function of setting the IP 5 times in the batchfile, it's only done twice (once because DHCP is a slightly 
different string), and takes input in the form of variables. That way each choice (or the command line 
arguments if used that way) can just 'call' that one 'function' (with gotos and labels) and have it do its work. This should deduplicate code which should save problems later on, even if using goto is bad.

I wonder if this will even make it easier to take more arguments than just IP via command line invocation?
That will probably be another branch.
