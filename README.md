# Azorult-Hunter
Azorult C&amp;C Hunter with bash onliner and nuclei yaml rule.

#Requirements
1. nuclei.
2. httprobe.

#Tutorial
Note:- run the below in your terminal.

curl -X GET "https://azorult-tracker.net/api/ip/" -H "accept: application/json" | tee -a azor.txt; cat azor.txt | grep -Eo '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | tee -a fil_azor.txt; cat fil_azor.txt | ./httprobe | tee -a probed_azor.txt

./nuclei -t azorult-detect.yaml -l probed_azor.txt -v | tee -a azor_out.txt

Now, change the path of the shell and location wordlist in the .yaml file

     shell: /home/<user>/Desktop/azor_shell.txt
      list: /home/<user>/Desktop/com.txt

#Read
Note: - "This is just a random experiment with nuclei yaml rule to detect azorult C&C , we don't take responsibilities of the damages done with this"

#Credit
1. D0rkerDevil - https://twitter.com/D0rkerDevil          
2. SubhajitSaha0x

