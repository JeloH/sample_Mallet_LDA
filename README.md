# sample_Mallet_LDA
../bin/mallet train-topics --num-topics 20 --input tutorial.mallet --evaluator-filename ev.di --num-iterations 100 --show-topics-interval 1000 --alpha 1 --beta .07

../bin/mallet evaluate-topics --evaluator ev.di --input tutorial.mallet --output-doc-probs docprobs.txt

../bin/mallet run cc.mallet.util.DocumentLengths --input tutorial.mallet  -doclengths.txt

1.creat file.mallet


2. split to training and testing
bin/mallet split --input tutorial.mallet --training-file training.mallet --testing-file testing.mallet --training-portion .8

3.

bin\mallet evaluate-topics --evaluator wiki_en.evaluator --input testing.mallet --output-doc-probs docprobs.dat



-----



\\\\generarw data and stow wprds
1-bin\mallet import-dir --input sample-data\web\en --output tutorial.mallet --keep-sequence  

/// testing and training
2. bin\mallet split --input tutorial.mallet --training-file training.mallet --testing-file testing.mallet --training-portion .8


3./// create evaluator file
-bin\mallet train-topics --num-topics 20 --input testing.mallet --evaluator-filename evaluator.evt --num-iterations 100 --show-topics-interval 1000 --al pha 1 --beta .07

/// creat probility file
-bin\mallet evaluate-topics --evaluator ev.di --input tutorial.mallet --output-doc-probs docprobs.txt

/// get lenght for docs
- bin\mallet run cc.mallet.util.DocumentLengths --input tutorial.mallet  doclengths.txt
