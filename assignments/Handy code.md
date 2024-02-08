Handy code

##### Open computing node for analyss

module load slurm/alpine
srun --partition atesting -t 1:00:00 --pty /bin/bash

#### NOTE:  need to activate fastp for each session

conda activate fastp

####  from your con-gen-csu directory

fastp -i data/fastqs/DPCh_plate1_B10_S22_R1.fq.gz -I data/fastqs/DPCh_plate1_B10_S22_R2.fq.gz \
-o results/qc/fastp/DPCh_plate1_B10_S22_R1.trimmed -O results/qc/fastp/DPCh_plate1_B10_S22_R2.trimmed \
-q 20 \
--adapter_sequence=AGATCGGAAGAGCACACGTCTGAACTCCAGTCA 
--adapter_sequence_r2=AGATCGGAAGAGCGTCGTGTAGGGAAAGAGTGT \ 
--detect_adapter_for_pe \
--cut_right --cut_right_window_size 4 --cut_right_mean_quality 20


#####  Alternative output to .fq.gz files

fastp -i data/fastqs/DPCh_plate1_B10_S22_R1.fq.gz -I data/fastqs/DPCh_plate1_B10_S22_R2.fq.gz \
-o results/qc/fastp/DPCh_plate1_B10_S22_R1.fq.gz -O results/qc/fastp/DPCh_plate1_B10_S22_R2.fq.gz \
-q 20 \
--adapter_sequence=AGATCGGAAGAGCACACGTCTGAACTCCAGTCA 
--adapter_sequence_r2=AGATCGGAAGAGCGTCGTGTAGGGAAAGAGTGT \ 
--detect_adapter_for_pe \
--cut_right --cut_right_window_size 4 --cut_right_mean_quality 20


####  end fastp

conda deactivate

#### exit node

exit


####Shell Self Study

The value of PHONE is: 974-222-4444
(base) [rbortner@colostate.edu@login11 shell]$ $PHONE
-bash: 974-222-4444: command not found
(base) [rbortner@colostate.edu@login11 shell]$ Good=i2
(base) [rbortner@colostate.edu@login11 shell]$ $Good
-bash: i2: command not found
(base) [rbortner@colostate.edu@login11 shell]$ cat $Good
cat: i2: No such file or directory
(base) [rbortner@colostate.edu@login11 shell]$ Bad=4this
(base) [rbortner@colostate.edu@login11 shell]$ $Bad
-bash: 4this: command not found
(base) [rbortner@colostate.edu@login11 shell]$ Bad=4THIS
(base) [rbortner@colostate.edu@login11 shell]$ $Bad
-bash: 4THIS: command not found
(base) [rbortner@colostate.edu@login11 shell]$ echo $Bad
4THIS
(base) [rbortner@colostate.edu@login11 shell]$ Bad=file-name
(base) [rbortner@colostate.edu@login11 shell]$ echo $Bad
file-name
(base) [rbortner@colostate.edu@login11 shell]$ Mandela_Quote="The greatest glory in living lies not in never falling, but in rising every time we fall."
(base) [rbortner@colostate.edu@login11 shell]$ echo $Mandela_Quote
The greatest glory in living lies not in never falling, but in rising every time we fall.
(base) [rbortner@colostate.edu@login11 shell]$ DESSERT="apple pie"
(base) [rbortner@colostate.edu@login11 shell]$ echo 'Dessert tonight is $DESSERT'
Dessert tonight is $DESSERT
(base) [rbortner@colostate.edu@login11 shell]$ DESSERT="apple pie"
(base) [rbortner@colostate.edu@login11 shell]$ echo "Dessert tonight is $DESSERT"
Dessert tonight is apple pie
(base) [rbortner@colostate.edu@login11 shell]$ NAME=Robyn
(base) [rbortner@colostate.edu@login11 shell]$ FOOD=spaghetti
(base) [rbortner@colostate.edu@login11 shell]$ ACTIVITY="horse-back riding"
(base) [rbortner@colostate.edu@login11 shell]$ echo "My name is $NAME. I like to eat $FOOD, and I enjoy $ACTIVITY."
My name is Robyn. I like to eat spaghetti, and I enjoy horse-back riding.
(base) [rbortner@colostate.edu@login11 shell]$

##add command to variable
MyComm="gzip -cd data/samtools_stats/s001_stats.tsv.gz"


## run pipes, etc. 
eval $MyComm 
