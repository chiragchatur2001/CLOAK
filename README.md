# CLOAK
A program for filtering Multiple Sequence Alignments (MSAs) 

CLOAK uses the intermediary alignments generated by the MUSCLE5 program as input. You can obtain the 16 intermediary alignments by using the following commands: 
./muscle.exe -align input.fasta -output stratified_ensemble.efa -stratified
This command generates a stratified ensemble file which contains all intermediary alignments. Then, run the following command: 
./muscle.exe -efa_explode stratified_ensemble.efa
This command generates 16 different intermediate files (abc.0, abc.1, abc.2, abc.3, acb.0, acb.1, acb.2, acb.3, bca.0, bca.1, bca.2, bca.3, none.0, none.1, none.2, none.3)
We recommend placing all 16 files into a directory (lets say you name it msa_directory)

Then, run the following command: 
python cloak.py /path/to/your/msa_directory

Running this command generates a file called msa_directory_result.fasta, which contains the filtered alignment. 
The result fasta file is generated in the same location from which the python script is run. 
