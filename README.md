1. The result: 
![alt text](img/image-1.2.png)
The done appeared 2 seconds after howdy, as expected and similar to previous experiment. The intereseting part here is that hey hey appeared first before howdy, even though howdy is placed before hey hey on the code lines. Right after running the spawn line, the program immediately continue to the next line, which is printing hey hey (without waiting for the async to even start running it's line). The async which is running in the background apparently prints howdy later than hey hey. Maybe even the spawning of async took some time (creating new threads and such?) and it's also run in the background, so the main program can continue to the next line.

2. When drop is commented out: 
![alt text](img/image-1.3-a.png)
When drop is back again: 
![alt text](img/image-1.3-b.png)
And another run with drop still there:
![alt text](img/image-1.3-c.png)
The program does not stop when drop is commented out. Without drop statement, the executor will still be waiting for a task to run. 
Also without the drop statement, seems like the done is not printed in order (it's not done, done2, done3 as expected). I tried running the no-drop version several times and the order seems quite random. 