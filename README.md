# Azorult-Hunter

Azorult C&amp;C Hunter is a threat detection tool written in bash onliner and nuclei YAML rule.
Note - you can use it with your own ip range / personal scans not just dependent on the api.

## Requirements

Find the installation steps in their documentation

1. [Nuclei](https://github.com/projectdiscovery/nuclei)
2. [Httprobe](https://github.com/tomnomnom/httprobe)


## Usage

```bash
# Fetch IPs from Azorult-Tracker
curl -X GET "https://azorult-tracker.net/api/ip/" -H "accept: application/json" | tee -a azor.txt; cat azor.txt | grep -Eo '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | tee -a fil_azor.txt; cat fil_azor.txt | ./httprobe | tee -a probed_azor.txt

#  For Output 
./nuclei -t azorult-detect.yaml -l probed_azor.txt -v | tee -a /azor_out.txt

# Make Sure to change the path of the shell and location of the wordlist in the .yaml file

     shell: /home/<user>/Desktop/azor_shell.txt
      list: /home/<user>/Desktop/com.txt      

# Path lists will be updated frequently !!
```

## Authors
• [D0rkerDevil](https://twitter.com/D0rkerDevil) 

• [SubhajitSaha0x](https://www.linkedin.com/in/subhajitsaha0x/)

Please make sure to give credits to authors if you are using this.

 This is for educational purposes, Authors are not responsible for any damages.
 
## License
[MIT](https://choosealicense.com/licenses/mit/)
