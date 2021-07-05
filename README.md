# Azorult-hunter
Azorult C&amp;C hunter with bash onliner and nuclei yaml rule.

#Requirements
1. nuclei.
2. httprobe.

#Tutorial
Note:- run the below in your terminal.

curl -X GET "https://azorult-tracker.net/api/ip/" -H "accept: application/json" | tee -a ~/Desktop/azor.txt; cat azor.txt | grep -Eo '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' | tee -a ~/Desktop/fil_azor.txt; cat ~/Desktop/fil_azor.txt | ~/Desktop/./httprobe | tee -a ~/Desktop/probed_azor.txt

./nuclei -t ~/Desktop/azorult-detect.yaml -l ~/Desktop/probed_azor.txt -v | tee -a ~/Desktop/azor_out.txt

#Please Note
Note: - "This is just a random experiment with nuclei yaml rule to detect azorult C&C , we don't take responsibilities of the damages done with this"

#Credit
1. D0rkerDevil - https://twitter.com/D0rkerDevil          


