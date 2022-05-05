## CSE15L Lab Reports (Spring 2022)

# Lab Report 3 W6
This lab report will cover implementing all Group Choice Options from Lab 5.

## Streamlining ssh Configuration
First thing to do is setup the config file in ~/.ssh/config. To do this I created a new file called "config" in my .ssh folder, edited with Notepad++, and added the lines seen in the image below.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20213906.png?raw=true)

And now just by typing "ssh ieng6" I can now log into my remote machine.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20214355.png?raw=true)

I can also use scp in a similar manner. 

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20214701.png?raw=true)

## Set up Github Access from ieng6
Next up is setting up Github Acces from the remote machine which is a bit more complicated. To do this I created a new public and private key on my remote machine.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20215157.png?raw=true)

And then after that I was just a matter of adding the public key to Github.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20215433.png?raw=true)

So now I can make changes and push to repos linked to my Github from my remote machine, which can be seen in [this](https://github.com/Badflar/markdown-parser/commit/7fc2ed320390224d8aa60831e2090c25fd645e84) commit.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20221141.png?raw=true)

## Copy whole directories with `scp -r`

Finally, copying an entire directory. To copy the markdown-parse project from my computer to the remote computer, I can do the following command:

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20222009.png?raw=true)

And then hopping over to the remote computer, I can run the code.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20222205.png?raw=true)

We can also do both of these steps in one gigantic command.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab%203/Screenshot%202022-05-04%20224853.png?raw=true)
