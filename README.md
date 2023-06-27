# SetIP
A batch script to set either DHCP or a variety of static IPs on Windows without futzing about with Settings!

This branch "modular" has basically the same functionality as v1.0, except instead of including the actual 
function of setting the IP 4 times in the batchfile, it's only done once, and takes input in the form of 
variables. That way each choice (or the command line arguments if used that way) can just 'call' that one 
'function' (with gotos and labels, it's not real modularity I know) and have it do its work. This should 
deduplicate code which should save problems later on, even if using goto is bad.

I wonder if this will even make it easier to take more arguments than just IP via command line invocation?
That will probably be another branch.
