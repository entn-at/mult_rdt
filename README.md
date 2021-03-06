   This package allows to extract features based on Region Dependent Transforms (RDT) models from audio files.
The features are well suitable mainly for Gaussian Mixture Models (GMM) in Automatic Speech Recognition (ASR) systems but they could be used in other applications as well.

The whole process could be split into 3 steps. Standard PLP-HLDA features are concatenated with Stacked Bottle-Neck Features trained in multilingual fashion on Babel data coming from 17 different languages.
This features are going into discriminatively trained RDT transforms on 17 Babel languages which generates final outputs.

It requies:
 -  STK with RDT extension, which can be downloaded by:
    git clone -b rd_xforms https://github.com/stk-developers/stk.git
      and follow manual  
 -  Kaldi: git clone https://github.com/kaldi-asr/kaldi.git
 -  RDT and NN models: http://www.fit.vutbr.cz/~karafiat/software/MultRDTv1.tar.gz


After instalation modify $KALDI_ROOT, $STKBIN, $RDTMODELS
in path.sh

and test the script by 
cd examples
../forward.single.sh -tmpdir tmpdir -rm F -tag 1089-134686-0019 data/test output


Current version of the script "forward.single.sh" can process only single wavfile "-tag wavname" and save the output file into "outdir" in HTK format.
In future is planing more clever version which process whole dir.
In case of any problem let me know.



Licence:

The models (pretrained networks) are released for noncommercial usage under CC BY-NC-ND 4.0 license (https://creativecommons.org/licenses/by-nc-nd/4.0/) and shell code under Apache 2.0 (https://www.apache.org/licenses/LICENSE-2.0). For any other use, please contact Jan Cernocky.

Citacion:
KARAFIAT Martin, BURGET Lukas, GREZL Frantisek, VESELY Karel and CERNOCKY Jan. Multilingual Region-Dependent Transforms
In Proceedings of the 41th IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP 2016), 2016. Shanghai: IEEE Signal Processing Society, 2016, pp. 5430-5434. ISBN 978-1-4799-9988-0.
Available from: http://www.fit.vutbr.cz/research/groups/speech/publi/2016/karafiat_icassp2016_0005430.pdf
