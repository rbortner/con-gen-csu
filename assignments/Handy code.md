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